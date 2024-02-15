pipeline {
    agent any

    tools {
        
        nodejs 'NodeJS'

        
        xvfb 'Xvfb'
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    
                    checkout scm
                }
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    
                    sh 'npm install'
                }
            }
        }

        stage('Run Cypress tests') {
            steps {
                script {
                    
                    sh 'npx cypress run'
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
