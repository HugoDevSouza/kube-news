pipeline{
    agent any

    stages{
        stage('Build Docker Image'){
            steps{
                script{
                    dockerapp = docker.build("hugoalves6121/kube-news:v1 ", '-f ./src/dockerfile ./src')
                }
            }
        }
    }
}

// # http://142.93.62.200:8080/job/kube-news/