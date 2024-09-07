pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                bat '''
                REM Add your build commands here (for Windows)
                echo Build complete
                '''
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat '''
                REM Add your test commands here (for Windows)
                echo Tests complete
                '''
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis...'
                echo 'Tool used: SonarQube'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                bat '''
                REM Add your deployment commands here (for Windows)
                echo Deployment complete
                '''
            }
        }
    }

    post {
        always {
            echo 'Pipeline complete.'
        }

        success {
            echo 'Pipeline succeeded!'
            mail to: 'andreiangeles738@gmail.com',
                 subject: "Jenkins Pipeline Success: ${env.JOB_NAME}",
                 body: "The Jenkins pipeline ${env.JOB_NAME} completed successfully."
        }

        failure {
            echo 'Pipeline failed!'
            mail to: 'andreiangeles738@gmail.com',
                 subject: "Jenkins Pipeline Failure: ${env.JOB_NAME}",
                 body: "The Jenkins pipeline ${env.JOB_NAME} failed. Check the logs for more details."
        }
    }
}
