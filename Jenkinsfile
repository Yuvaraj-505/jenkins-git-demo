pipeline {
    agent any

    stages {

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
