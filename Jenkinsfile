pipeline {
    agent any

    parameters {
        string(
            name: 'USER_NAME',
            defaultValue: 'Dhaxina',
            description: 'Enter your name'
        )

        choice(
            name: 'ENVIRONMENT',
            choices: ['Development', 'Testing', 'Staging', 'Production'],
            description: 'Select deployment environment'
        )

        booleanParam(
            name: 'RUN_TESTS',
            defaultValue: true,
            description: 'Run Unit Tests'
        )

        password(
            name: 'DB_PASSWORD',
            defaultValue: '',
            description: 'Enter database password'
        )
    }

    environment {
        PROJECT_NAME = "jenkins-git-demo"
        OWNER = "Dhaxina"
    }

    stages {

        stage('Credentials Demo') {
            steps {

            withCredentials([
            string(
                credentialsId: 'demo-token',
                variable: 'TOKEN'
            )
            ]) {

                sh '''
                echo "Credential loaded successfully."
                echo "Length of token:"
                echo ${#TOKEN}
                '''
                sh 'echo $TOKEN'

                }
            }
        }

        stage('Environment Demo') {

            steps {
                sh 'echo "Project: $PROJECT_NAME"'
                sh 'echo "Owner: $OWNER"'
            }
        }

        stage('String Parameter Demo') {
            steps {
                echo "Hello ${params.USER_NAME}"
                sh 'echo "Hello from Shell: $USER_NAME"'
            }
        }

        stage('Choice Parameter Demo') {
            steps {
                echo "Selected: ${params.ENVIRONMENT}"
                sh 'echo "Shell Value: $ENVIRONMENT"'
            }
        }

        stage('Boolean Parameter Demo') {
            steps {
                echo "Run Tests = ${params.RUN_TESTS}"
            }
        }

        stage('Run Tests') {
            when {
                expression {
                    return params.RUN_TESTS
                }
            }

            steps {
                sh 'echo "Executing Unit Tests..."'
            }
        }

        stage('Connect Database') {
            steps {
                sh '''
                    echo "Connecting to database..."
                    # Use the password here
                '''
            }
        }

        // stage('Fail Demo') {
        //     steps {
        //     sh 'exit 1'
        //     }
        // }

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

    post {

        success {
            echo "Build completed successfully!"
        }

        failure {
            echo "Build failed!"
        }

        always {
            echo "Post block execution completed."
        }

    }


}
