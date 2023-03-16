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
                stage('Test Chrome - Windows 11') {
                    steps {
                        echo 'npm run test: Windows - integration:chrome'
                    }
                }
                stage('Test Chrome - Mac 11') {
                    steps {
                        echo 'npm run test: Mac - integration:chrome'
                    }
                }
            }
        }

        stage('Deploy to QA') {

            steps {
                echo 'npm run deploy:qa'
            }
        }
        stage('User Acceptance Tests (UAT)') {
            parallel {
                stage('Test Chrome - Windows 11') {
                    steps {
                        echo 'npm run test: Windows - integration:chrome'
                    }
                }
                stage('Test Chrome - Mac 11') {
                    steps {
                        echo 'npm run test: Mac - integration:chrome'
                    }
                }
                stage('Test Firefox - Windows 11') {
                    steps {
                        echo 'npm run test:integration:firefox'

                    }
                }
                stage('Test Firefox - Windows 10') {
                    steps {
                        echo 'npm run test:integration:firefox'
                    }
                }
                stage('Test Firefox - Mac') {
                    steps {
                        echo 'npm run test:integration:firefox'
                    }
                }
                stage('Test Safari') {
                    steps {
                        echo 'npm run test:integration:safari'
                    }
                }
            }
        }
        stage('Deploy to Production') {

            steps {
                echo 'npm run deploy:prod'
            }
        }
    }
}
