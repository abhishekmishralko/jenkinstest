# jenkinstest
# basic jenkins file 
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from SCM (e.g., Git)
                git branch: 'main', url: 'https://github.com/your-repo/your-project.git'
            }
        }

        stage('Build') {
            steps {
                // Run build steps
                echo 'Building...'
                // Add your build commands here, e.g., sh 'make'
            }
        }

        stage('Test') {
            steps {
                // Run test steps
                echo 'Testing...'
                // Add your test commands here, e.g., sh 'make test'
            }
        }

        stage('Deploy') {
            steps {
                // Run deploy steps
                echo 'Deploying...'
                // Add your deploy commands here, e.g., sh 'make deploy'
            }
        }
    }

    post {
        always {
            // Actions that are always executed after the pipeline runs
            echo 'Cleaning up...'
            // Add any cleanup steps here
        }
        success {
            // Actions that are executed on successful pipeline run
            echo 'Pipeline succeeded!'
        }
        failure {
            // Actions that are executed on failed pipeline run
            echo 'Pipeline failed!'
        }
    }
}
