pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker build -t adijaiswal/currencyservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                     sh "docker tag adijaiswal/currencyservice:latest cary01/kirtan1:currencyservicetag"
                       sh "docker push cary01/kirtan1:currencyservicetag"
                    }
                }
            }
        }
    }
}
