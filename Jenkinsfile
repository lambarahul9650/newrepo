pipeline {
    agent any

    stages{
        stage ('checking docker') {

            steps {
                sh 'docker --version'

            }
        }

        stage ('building image') {

            steps {
                sh 'docker build . -t lambarahul298/text:01'
                
            }
        }

        stage ('Publish Docker Hub') {

            steps {
                sh 'docker push lambarahul298/text:01'
                
            }
        }
        
    }
}