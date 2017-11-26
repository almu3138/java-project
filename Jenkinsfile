properties([pipelineTriggers([githubPush()])])

node('master') {   
    stage('Tests') { 
      sh 'ant'
      sh 'ant -f test.xml -v'
      junit 'reports/result.xml'
	}   
