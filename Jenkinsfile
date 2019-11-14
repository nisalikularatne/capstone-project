pipeline {
agent any
stages{
 stage ('Clone your github repository') {
 steps{
      git 'https://github.com/nisalikularatne/capstone-project.git'
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