pipeline {
    agent any

    tools {
        // Define NodeJS tool with the name 'NodeJS'
        nodejs 'NodeJS'

        // Define Xvfb tool with the correct name 'Xvfb'
        xvfb 'Xvfb'
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    // Checkout the source code
                    checkout scm
                }
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // This should now work if NodeJS is properly configured
                    sh 'npm install'
                }
            }
        }

        stage('Run Cypress tests') {
            steps {
                script {
                    // Run Cypress tests with Xvfb
                    sh 'xvfb-run --auto-servernum npx cypress run'
                }
            }
        }
    }

    post {
        always {
            // Clean up
            deleteDir()
        }
    }
}
