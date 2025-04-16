pipeline {
    agent any
}

environment {
    COMPOSE_PROJECT_NAME = "mern-docker-compose"
}

stages{
    stage('checkout code') { 
     steps {
        git 'https://github.com/Sharmeeh/MERN-docker-compose.git'

     }   
    }

    stage('Build and run with Docker Compose') { 
     steps {
        sh 'docker compose down'
        sh 'docker compose up -d --build'

     }   
    }

}