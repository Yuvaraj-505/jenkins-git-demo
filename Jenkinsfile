pipeline {
    agent any

    environment {
        PROJECT_NAME = "jenkins-git-demo"
        OWNER = "Dhaxina"
    }

    stages {

        stage('Environment Demo') {

            environment {
                MY_STAGE_NAME = "Environment Demo Stage"
            }

            steps {
                sh 'echo "Project: $PROJECT_NAME"'
                sh 'echo "Owner: $OWNER"'
                sh 'echo "My Stage: $MY_STAGE_NAME"'
            }
        }

        stage('Current Directory') {
            steps {
                sh 'echo "Project: $PROJECT_NAME"'
                sh 'echo "Owner: $OWNER"'
                sh 'echo "My Stage: $MY_STAGE_NAME"'
                sh 'pwd'
            }
        }

        stage('List all files') {
            steps {
                sh 'ls -la'
            }
        }

        stage('Read README') {
            steps {
                sh 'cat README.md'
            }
        }
    }
}
