properties([pipelineTriggers([githubPush()])])

node('linux') {   
    stage('Unit Tests') { 
      junit 'ant'
      sh 'ant -f test.xml -v'
      junit 'reports/result.xml'
	
    }

    stage('Build') {    
	sh 'ant'
	sh 'ant -f build.xml -v'
	
    }

	stage('Deploy') {
   	sh 'jenkins-s3bucket-izg9ekp07zqm.s3.amazonaws.com'
	}
    
}
