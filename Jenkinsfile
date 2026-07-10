pipeline {
    agent any

    environment {
        PROJECT_NAME = "jenkins-git-demo"
        OWNER = "Dhaxina"
    }

    stages {

        stahe('Environment Demo') {
            steps {
                sh 'echo "Project: $PROJECT_NAME"'
                sh 'echo "Owner: $OWNER"'
            }
        }

        stage('Current Directory') {
            steps {
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
