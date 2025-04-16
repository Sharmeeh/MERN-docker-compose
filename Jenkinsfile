pipeline {
    agent any

    environment {
        COMPOSE_PROJECT_NAME = "myapp"
    }

    stages {
        stage('Checkout Code') {
            steps {
                git url: 'https://github.com/your-user/your-docker-compose-repo.git'
            }
        }

        stage('Build & Run with Docker Compose') {
            steps {
                sh 'docker-compose down' // Cleanup if needed
                sh 'docker-compose up -d --build'
            }
        }

    }
}