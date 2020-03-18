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
	triggers {
           	upstream 'test1'
	}

	environment{
		some_name="jeff"
	}	
    stages {
        stage('Master branch') {
            when {
                branch 'master'
            }
            steps {
			sh	'echo "${some_name}'
            }
        }
        stage('Equal expected') {
            when {
                equals expected: "jeff", actual: some_name
            }
            steps {
				sh 'echo "${some_name}"'
            }
        }
        stage('Dev branch') {
            when {
                branch 'dev'
            }
            steps {
				sh 'echo "${some_name}"'
            }
        }
    }
}
