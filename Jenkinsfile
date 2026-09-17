pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/kavin82007/Jenkins-Parallel-Pipeline.git'
            }
        }

        stage('Parallel Checks') {
            parallel {

                stage('Frontend Check') {
                    steps {
                        bat 'python frontend_check.py'
                    }
                }

                stage('Backend Check') {
                    steps {
                        bat 'python backend_check.py'
                    }
                }
            }
        }

        stage('Summary') {
            steps {
                echo 'Both frontend and backend checks are complete.'
            }
        }
    }
}