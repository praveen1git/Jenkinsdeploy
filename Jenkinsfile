pipeline {
     agent any
environment {
    IMAGE_REPO = "praveen1git"
}     
     stages {
         stage('Build Docker Image') {
              steps {
                  sh "ls"
                  sh " docker image build -t  ${env.IMAGE_REPO}:${env.GIT_COMMIT} ."
              }
         }
         stage('deploy latesh image') {
              steps {
                  sh "docker stop demo"
                  sh "docker rm demo "
                  sh "docker run --restart always --name demo -p 5001:5001 -d ${env.IMAGE_REPO}:${env.GIT_COMMIT}"
              }
         }
             }
        }
