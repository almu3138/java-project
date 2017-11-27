properties([pipelineTriggers([githubPush()])])

node('linux') { 
       
    stage('Unit Tests') { 
      git 'https://github.com/almu3138/java-project.git'
      sh 'ant'
      sh 'ant -f test.xml -v'
      junit 'reports/result.xml'
	
    }

    stage('Build') {    
	sh 'ant'
	sh 'ant -f build.xml -v'
	
    }

    stage('Deploy') {
   	  aws s3 cp *.jar /jenkins-s3bucket-izg9ekp07zqm/
		  
      }
    
    stage('Report') {
		withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: '964b912d-3db4-4264-9fa1-e9cef340ce8d', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
                sh 'aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins'
           }
	}

}
