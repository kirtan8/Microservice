pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker build -t adijaiswal/frontend:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                     sh "docker tag adijaiswal/frontend:latest cary01/kirtan1:frontendtag"
                       sh "docker push cary01/kirtan1:frontendtag"
                    }
                }
            }
        }
    }
}
