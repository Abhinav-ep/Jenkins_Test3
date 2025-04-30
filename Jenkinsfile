pipeline {
    agent any

    stages {
        stage('Deploy to Minikube') {
            steps {
                withCredentials([file(credentialsId: 'kubeconfig-minikube', variable: 'KUBECONFIG')]) {
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
