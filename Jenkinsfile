pipeline{
    agent any
    stages{
        stage('Clone Repository'){
            steps{
                git branch : 'main' , url:'https://github.com/nibamuskan/ci-node-app.git'
            }
        }
        stage('Build Docker Image'){
            steps{
                bat 'docker build -t ci-node-app .'
            }
        }
        stage('Run Docker Containers'){
            steps{
                bat 'docker run -d -p 8080:80 --name web-container ci-node-app'
            }
        }
    }
}