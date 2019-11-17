
pipeline {
  environment {
    registry = "nisalikularatne/capstone-docker"
    registryCredential = 'dockerhub'
  }
  agent any
  stages {
  stage ('Clone your github repository') {
   steps{
        git 'https://github.com/nisalikularatne/capstone-project.git'
      }
     }
     stage('Build Docker Image') {
                when {
                    branch 'master'
                }
                steps {
                    script {
                        sudo sh 'docker build . -t nisalikularatne/capstone-docker'
                        }
                    }
             }
  }
}