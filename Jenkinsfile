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
                sh 'docker build -t devopsbyritesh .'
            }
        }

        stage('Tag & Push'){
            steps{
                withDockerRegistry(credentialsId: 'dockerhub', url: 'https://index.docker.io/v1/') {
                    sh 'docker tag devopsbyritesh riteshprasad07/devopsbyritesh:v1'
                    sh 'docker push riteshprasad07/devopsbyritesh:v1'
                }
            }
        }
    }
}





