pipeline {
    agent any
	environment{
		some_name="jeff"
	}	
    stages {
        stage('Master branch') {
            when {
                branch 'master'
            }
            steps {
		    		echo "Master Stage"
				echo "${some_name}"
            }
        }
        stage('Equal expected') {
            when {
                equals expected: "jeff", actual: some_name
            }
            steps {
		    		echo "Equal Expected Stage"
				echo "${some_name}"
            }
        }
        stage('Dev branch') {
            when {
                branch 'dev'
            }
            steps {
		    		echo "Dev Stage"
				echo "${some_name}"
            }
        }
    }
}
