pipeline {
    agent any

    stages {

        stage('Current Directory') {
            steps {
                sh 'pwd'
            }
        }

        stage('List Files') {
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
