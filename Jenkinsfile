pipeline {
    agent any
    
    stages {
        stage('Sync the Repo') {
            steps {
                sh 'git pull'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t microservice-k8s:latest .'
            }
        }
        
        stage('Deploy on Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yml'
            }
        }
    }
}
