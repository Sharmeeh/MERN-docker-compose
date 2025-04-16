pipeline {
  agent any

  environment {
    COMPOSE_PROJECT_NAME = "mern_app"
  }

  stages {
    stage('Checkout Code') {
      steps {
        // Replace with your Git repo URL
        git url:'https://github.com/Sharmeeh/MERN-docker-compose.git' , branch: 'compose'
      }
    }

    stage('Build & Start Containers') {
      steps {
        sh 'docker-compose up'
      }
    }

    stage('Verify Backend is Running') {
      steps {
        sh 'docker-compose ps'
        sh 'docker-compose logs backend'
      }
    }

    stage('Teardown') {
      steps {
        sh 'docker-compose down'
      }
    }
  }
  
}
          