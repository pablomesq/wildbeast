pipeline {
    agent any
    
    stages {
        stage('Build docker image') {
            steps {
                // sh 'echo "Executando o comando Docker Build"'
                script {
                    dockerapp = docker.build("pabloapache/jenkins-wildbeast:${env.BUILD_ID}", "-f ./docker/dockerfile.dev .")
                }
            }
        }

        stage('Push docker image') {
            steps {
                // sh 'echo "Executando o comando Docker Push"'
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                        dockerapp.push("latest")
                        dockerapp.push("${env.BUILD_ID}")
                    }
                }
            }
        }

        stage('Deploy no Kubernetes') {
            environment {
                tag_version = "${env.BUILD_ID}"
            }
            steps {
                // sh 'echo "Executando o comando Kubectl apply"'
                withKubeConfig([credentialsId: 'kubeconfig']){
                    sh 'sed -i "s/{{tag}}/$tag_version/g" ./k8s/deployment.yaml'
                    sh 'kubectl apply -f ./k8s/deployment.yaml'
                }
                
            }
        }
    }
}