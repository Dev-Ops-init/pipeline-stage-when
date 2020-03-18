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
	environment{
		some_name="jeff"
	}	
    stages {
        stage('Master branch') {
            when {
                changeset '*/*.json'
            }
            steps {
				echo "${some_name}
            }
        }
        stage('Dev branch') {
            when {
                branch 'dev'
            }
            steps {
				echo "${some_name}"
            }
        }
    }
}
