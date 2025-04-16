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
        sh 'docker compose up'
      }
    }

    stage('Verify Backend is Running') {
      steps {
        sh 'docker compose ps'
        sh 'docker compose logs backend'
      }
    }
  }

  post {
    always {
      echo "Pipeline completed. You can now access the frontend at http://172.26.96.12:5173"
    }
  }
}
          