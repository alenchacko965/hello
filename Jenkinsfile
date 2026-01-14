pipeline {
  agent any

  stages{
    stages('Stop old Container'){
      steps {
        bat 'docker rm -f hello || exit 0'
      }
    }
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
    stage('Run docker container') {
      steps{
        echo 'Running Docker container'
        bat 'docker run -d -p 8070:80 hello '
      }
    }
  }
}  
