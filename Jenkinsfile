
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
         	     	sh "docker tag first-docker-application nisalikularatne/first-docker-application"
         	     	sh "docker push nisalikularatne/first-docker-application"
         }
       }
     }
     stage('Deploy image to EKS cluster') {
           steps {
             withAWS(region:'us-west-2', credentials:'blueocean') {
                 sh '''aws --region us-west-2 eks update-kubeconfig --name UdacityEKSCapstone'''
     	         sh '''kubectl get nodes'''

      	         sh ''' kubectl run first-docker-application --image=nisalikularatne/first-docker-application --port=80'''
                 sh '''kubectl set image deployment/first-docker-application first-docker-application=nisalikularatne/first-docker-application"'''
     	          sh '''kubectl rollout status -w deployment/first-docker-application'''
     	          sh '''kubectl scale deployments/first-docker-application --replicas=3'''
     	          sh '''kubectl get pods -o wide'''
     	          sh '''kubectl describe deployment first-docker-application'''
             }
           }
          }
  }
}