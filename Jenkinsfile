properties([pipelineTriggers([githubPush()])])

node('master') {   
	stage('Unit Tests') { 
      sh 'ant'
      sh 'ant -f test.xml -v'
      junit 'reports/result.xml'
	}   
