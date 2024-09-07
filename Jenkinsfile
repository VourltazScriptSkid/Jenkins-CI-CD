pipeline {
    agent any

    stages {
        // Checkout the code from GitHub
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }

        // Build the project
        stage('Build') {
            steps {
                echo 'Building the application...'
                // Basic build step. Replace with your actual build command if needed.
                bat 'echo Build step complete' // Placeholder for the build command
            }
        }

        // Run unit tests
        stage('Test') {
            steps {
                echo 'Running tests...'
                // Basic test step. Replace with your actual test command if needed.
                bat 'echo Test step complete' // Placeholder for the test command
            }
        }

        // Deploy the application (this is kept simple and local for now)
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Simple deployment step, adjust to your actual deployment command
                bat 'echo Deploy step complete' // Placeholder for the deploy command
            }
        }
    }

    // Post actions to notify via email after success or failure
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
