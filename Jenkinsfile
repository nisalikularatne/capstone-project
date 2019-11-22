
pipeline {
  environment {
    registry = "nisalikularatne/first-docker-application"
    registryCredential = 'dockerhub'
  }
  agent any
  stages {
  stage ('Clone your github repository') {
   steps{
        git 'https://github.com/nisalikularatne/capstone-project.git'
      }
     }
    stage('Building image') {
      steps{
        script {
          sh 'docker build --tag=first-docker-application .'
        }
      }
    }
    stage('Push image'){
      steps{
        script{
         sh "docker login -u nisalikularatne -p NIS23141234KUL"
         	     	sh "docker build -t first-docker-application ."
         	     	sh "docker tag first-docker-application first-docker-application"
         	     	sh "docker push first-docker-application"
         }
       }
     }
  }
}