pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {

                parallel(
                    a: {
                        echo 'Testing in Chrome..'

                    }
                    b: {

                    }

                )

            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}