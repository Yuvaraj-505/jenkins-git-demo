pipeline {
    agent any

    parameters {
        string(
            name: 'USER_NAME',
            defaultValue: 'Dhaxina',
            description: 'Enter your name'
        )
    }

    environment {
        PROJECT_NAME = "jenkins-git-demo"
        OWNER = "Dhaxina"
    }

    stages {

        stage('Parameter Demo') {
            steps {
                echo "Hello ${params.USER_NAME}"
                sh 'echo "Hello from Shell: $USER_NAME"'
            }
        }

        stage('Environment Demo') {

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
