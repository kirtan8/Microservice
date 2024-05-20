pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker build -t adijaiswal/emailservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                     sh "docker tag adijaiswal/emailservice:latest cary01/kirtan1:emailservicetag"
                       sh "docker push cary01/kirtan1:emailservicetag"
                    }
                }
            }
        }
    }
}
