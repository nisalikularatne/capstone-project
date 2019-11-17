pipeline {
environment {
    registry = "nisalikularatne/capstone-docker"
    registryCredential = 'dockerhub'
  }
agent any
stages{
 stage ('Clone your github repository') {
 steps{
      git 'https://github.com/nisalikularatne/capstone-project.git'
    }
   }

stage('Build'){
steps{
 script {
         sudo docker.build registry + ":$BUILD_NUMBER"
        }

}
}
}
}

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
          docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
  }
}