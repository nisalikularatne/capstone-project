pipeline {
environment {
    registry = "docker_hub_account/repository_name"
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
          docker.build registry + ":$BUILD_NUMBER"
        }

}
}
}
}