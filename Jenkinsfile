
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
          sudo docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
  }
}