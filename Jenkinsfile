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

         stage ('pull docker image') {

            steps {
                sh 'docker pull lambarahul298/text:01'
                
            }
        }
        
         stage ('Docker run') {

            steps {
                sh 'docker run -d --name=nginx -p 9090:80 lambarahul298/text:01'
                
            }
        }
    }
}