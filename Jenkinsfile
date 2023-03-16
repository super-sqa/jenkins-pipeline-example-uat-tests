pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }

        stage('Unit Tests') {
            parallel {
                stage('Test Chrome') {
                    steps {
                        sh 'npm run test:chrome'
                    }
                }
                stage('Test Firefox') {
                    steps {
                        sh 'npm run test:firefox'
                    }
                }
            }
        }

        stage('Integration Tests') {
            parallel {
                stage('Test Chrome') {
                    steps {
                        sh 'npm run test:integration:chrome'
                    }
                }
                stage('Test Firefox') {
                    steps {
                        sh 'npm run test:integration:firefox'
                    }
                }
            }
        }

        stage('Deploy to QA') {
            when {
                branch 'develop'
            }
            steps {
                sh 'npm run deploy:qa'
            }
        }

        stage('Deploy to Production') {
            when {
                branch 'main'
            }
            steps {
                sh 'npm run deploy:prod'
            }
        }
    }
}
