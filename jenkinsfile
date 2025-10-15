pipeline {
    agent any
    
    stages {
        stage('Build docker image') {
            steps {
                sh 'echo "Executando o comando Docker Build"'
            }
        }

        stage('Push docker image') {
            steps {
                sh 'echo "Executando o comando Docker Push"'
            }
        }

        stage('Deploy no Kubernetes') {
            steps {
                sh 'echo "Executando o comando Kubectl apply"'
            }
        }
    }
}