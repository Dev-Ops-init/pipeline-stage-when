properties([
    buildDiscarder(
        logRotator(
            artifactNumToKeepStr: '20',
            numToKeepStr: '20')
    ),
    disableConcurrentBuilds()
])
pipeline {
    agent any	
    stages {
        stage('Condition branch') {
            when {
                changeset "*.json"
            }
            steps {
		    sh 'cat test.json'
            }
        }
        stage('Dev branch') {
            when {
                branch 'change-set'
            }
            steps {
		echo "Hello World : Condition branch"
	    }
        }
    }
}
