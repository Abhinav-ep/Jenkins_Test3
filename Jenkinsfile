pipeline {
    agent any

    environment {
        KUBECONFIG = "${HOME}/.kube/config"
    }

    stages {
        stage('Deploy to Minikube') {
            steps {
                script {
                    sh 'kubectl apply -f Files/nginx-deployment.yaml'
                    sh 'kubectl apply -f Files/nginx-service.yaml'
                }
            }
        }
    }

    post {
        success {
            echo '✅ Deployment successful!'
        }
        failure {
            echo '❌ Deployment failed.'
        }
    }
}
