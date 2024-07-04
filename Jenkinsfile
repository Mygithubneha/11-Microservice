pipeline {
    agent any

    stages {
        stage('Dey to Kernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: ' EKS-1', contextName: '', credentialsId: 'k8s-token', namespace: 'webapps', serverUrl: 'https://06138954EABB819F57865DFD28498F7A.yl4.ap-south-1.eks.amazonaws.com']]) {
                        sh "kubectl apply -f deployment-service.yml"
                }
            }
        }
        
        stage('Verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: ' EKS-1', contextName: '', credentialsId: 'k8s-token', namespace: 'webapps', serverUrl: 'https://06138954EABB819F57865DFD28498F7A.yl4.ap-south-1.eks.amazonaws.com']]) {
                        sh "kubectl get svc -n webapps"
                }
            }
        }
        
        
    }
}
