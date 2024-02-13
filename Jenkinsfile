pipeline {
    agent any

    tools {
        nodejs 'NodeJS'
    }

    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    // This should now work if NodeJS is properly configured
                    sh 'npm install'
                }
            }
        }

        stage('Checkout') {
            steps {
                script {
                    // Checkout the source code
                    checkout scm
                }
            }
        }

        stage('Install dependencies') {
            steps {
                script {
                    
                    // Install Node.js and Cypress dependencies
                    sh 'npm install'
                }
            }
        }

        stage('Run Cypress tests') {
            steps {
                script {
                   xvfbRun('npx cypress run')
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
