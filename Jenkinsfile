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
                bat 'docker run -d -p 3000:3000 --name node-container ci-node-app'
            }
        }
    }
}