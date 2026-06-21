pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Ritesh-Prasad/project-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devopsbyritesh07 .'
            }
        }

        stage('Tag & Push'){
            steps{
                withDockerRegistry(credentialsId: 'dockerhub', url: 'https://index.docker.io/v1/') {
                    sh 'docker tag devopsbyritesh07 riteshprasad07/devopsbyritesh07:v3'
                    sh 'docker push riteshprasad07/devopsbyritesh07:v3'
                }
            }
        }
    }
}





