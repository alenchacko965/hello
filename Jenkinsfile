pipeline {
  agent any

  stages{
    stages('Checkout Code') {
      steps {
        echo 'Pulling cdoe from Github'
        checkout scm
      }
    }
    stage('Build Docker Image') {
      steps {
        echo 'Building Docker Image'
        bat 'docker build -t hello .'
      }
    }
  }
}  
