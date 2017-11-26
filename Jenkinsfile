properties([pipelineTriggers([githubPush()])])

node('master') {   
    stage('Unit Tests') { 
      junit 'ant'
      sh 'ant -f test.xml -v'
      junit 'reports/result.xml'
	}   
