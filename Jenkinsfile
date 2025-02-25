pipeline {
    agent any
    environment {
        KUBECONFIG = credentials('k8-token') // Ensure this credential exists
    }
    stages {
        stage('Deploy To Kubernetes') {
            steps {
                script {
                    withKubeCredentials([credentialsId: 'k8-token', namespace: 'webapps']) {
                        // Your kubectl deployment logic
                    }
                }
            }
        }
    }
}


