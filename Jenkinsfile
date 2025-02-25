pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(credentialsId: 'k8-token') {
                    sh "kubectl apply -f deployment-service.yml"
                }
            }
        }

        stage('Verify Deployment') {
            steps {
                withKubeCredentials(credentialsId: 'k8-token') {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}


