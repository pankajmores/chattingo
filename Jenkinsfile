pipeline {
    agent any
    
    stages {
        stage('Git Clone') {
            steps {
                git 'https://github.com/YOUR_USERNAME/chattingo.git'
            }
        }
        
        stage('Build Images') {
            steps {
                sh 'docker build -t chattingo-frontend ./frontend'
                sh 'docker build -t chattingo-backend ./backend'
            }
        }
        
        stage('Push to Docker Hub') {
            steps {
                sh 'docker login -u YOUR_DOCKERHUB_USERNAME -p YOUR_DOCKERHUB_PASSWORD'
                sh 'docker push YOUR_DOCKERHUB_USERNAME/chattingo-frontend:latest'
                sh 'docker push YOUR_DOCKERHUB_USERNAME/chattingo-backend:latest'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'ssh USER@VPS_IP "cd /home/USER/chattingo && docker-compose pull && docker-compose up -d"'
            }
        }
    }
}
