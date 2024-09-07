pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'pip install -r requirements.txt'  // If your project has dependencies
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'python -m unittest discover'  // Example for running Python tests
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
            }
        }
    }

    post {
        success {
            echo 'The pipeline completed successfully!'
        }
        failure {
            echo 'The pipeline failed.'
        }
    }
}
