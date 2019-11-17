
pipeline {
  environment {
    registry = "nisalikularatne/capstone-docker"
    registryCredential = 'dockerhub'
  }
  agent any
  stages {
    stage('Building image') {
      steps{
        script {
          sudo docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
  }
}