pipeline {
    agent any

    stages {
        stage('Debug') {
    steps {
        script {
            sh 'node --version'
            sh 'npm --version'
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
                    // Run Cypress tests
                    sh 'npm run cy:run'
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
