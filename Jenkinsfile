properties([pipelineTriggers([githubPush()])])

node('top') {   
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
	
    }
