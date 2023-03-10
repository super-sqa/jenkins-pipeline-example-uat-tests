pipeline {
    agent none
    stages {
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {

                    steps {
                        echo "run-tests.bat"
                    }
                    post {
                        always {
                            echo "**/TEST-*.xml"
                        }
                    }
                }
                stage('Test On Linux') {

                    steps {
                        echo "run-tests.sh"
                    }
                    post {
                        always {
                            echo "**/TEST-*.xml"
                        }
                    }
                }
            }
        }
    }
}