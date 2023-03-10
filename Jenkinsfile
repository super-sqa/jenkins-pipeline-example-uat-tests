pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }

        stage ('UAT Test......') {
        parallel {
            stage('Testing in Chrome....') {
                        echo 'Testing in Chrome..'
            }

            stage('Testing in Firefox....') {
                        echo 'Testing in Firefox..'
            }
                

            }
            
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}