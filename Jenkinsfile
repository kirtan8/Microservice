pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    dir('src') {

                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker build -t adijaiswal/cartservice:latest ."
                    }
                        }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                      sh "docker tag adijaiswal/cartservice:latest cary01/kirtan1:cartservicetag"
                       sh "docker push cary01/kirtan1:cartservicetag"
                    }
                }
            }
        }
    }
}
