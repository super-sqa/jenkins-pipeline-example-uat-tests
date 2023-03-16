pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'installing...'
                echo 'building ...'
            }
        }

        stage('Unit Tests') {
            parallel {
                stage('Test Chrome') {
                    steps {
                        echo 'npm run test:chrome'
                    }
                }
                stage('Test Firefox') {
                    steps {
                        echo 'npm run test:firefox'
                    }
                }
            }
        }

        stage('Integration Tests') {
            parallel {
                stage('Test Chrome') {
                    steps {
                        echo 'npm run test:integration:chrome'
                    }
                }
                stage('Test Firefox') {
                    steps {
                        echo 'npm run test:integration:firefox'
                        echo 'npm run test:integration:firefox-1.2'
                        echo 'npm run test:integration:firefox-1.2'
                    }
                }
            }
        }

        stage('Deploy to QA') {
            // when {
            //     branch 'main'
            // }
            steps {
                echo 'npm run deploy:qa'
            }
        }

        stage('Deploy to Production') {
            // when {
            //     branch 'main'
            // }
            steps {
                echo 'npm run deploy:prod'
            }
        }
    }
}
