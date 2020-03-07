pipeline {
    agent any
    environment {
        PROJECT_ID = 'gaurav-devops-project-1'
        CLUSTER_NAME = 'sprint6-cluster1'
        LOCATION = 'us-central1-c'
        CREDENTIALS_ID = 'gaurav-devops-project-1'
    }
    stages {
        stage('Deploy to GKE') {
            steps{
                step([
                $class: 'KubernetesEngineBuilder',
                projectId: env.PROJECT_ID,
                clusterName: env.CLUSTER_NAME,
                location: env.LOCATION,
                manifestPattern: 'manifest.yaml',
                credentialsId: env.CREDENTIALS_ID,
                verifyDeployments: true])
            }
        }
    }
}
