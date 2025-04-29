pipeline {
    agent any

    environment {
        KUBECONFIG = "${HOME}/.kube/config"
    }

    stages {
        stage('Deploy to Minikube') {
            steps {
                script {
                    sh 'kubectl apply -f nginx-deployment.yaml'
                    sh 'kubectl apply -f nginx-service.yaml'
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
