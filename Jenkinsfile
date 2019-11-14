pipeline {
agent any
stages{
 stage ('Clone your github repository') {
 steps{
      git 'https://github.com/nisalikularatne/capstone-project.git'
    }
   }
stage ('Linting Dockerfile before build') {
    steps{
      sh '''docker run --rm -i hadolint/hadolint < Dockerfile'''
    }
   }
stage('Build'){
steps{
sh ' echo "Hello World"'
sh '''
   echo "Multiline shell steps works too"
   ls -lah
   '''
}
}
}
}