pipeline{
    agent any

    stages{

        stage('Build Docker Image'){
            steps{
                script{
                    dockerapp = docker.build("hugoalves6121/kube-news:${env.BUILD_ID}",'-f ./src/dockerfile ./src')
                }
            }
        }

        stage('Push Docker Image'){
            steps{
                script{
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub'){
                    dockerapp.push('latest')
                    dockerapp.push("${env.BUILD_ID}")
                    }
                }
            }
        }
    }


}

// # http://142.93.62.200:8080/job/kube-news/