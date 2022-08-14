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

         stage ('pull docker image on another server') {

            steps {

                sh 'ssh ubuntu@3.24.242.1 docker pull lambarahul298/text:01'
                
            }
        }
        
         stage ('Docker run on another server ') {

            steps {
                sh 'ssh ubuntu@3.24.242.1 docker run -d --name=nginx1 -p 9090:80 lambarahul298/text:01'
                
            }
        }
    }
}