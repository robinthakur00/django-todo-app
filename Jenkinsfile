pipeline {
    agent any
    stages {
        
        stage("Code Fetch From Git"){
            steps{
                git url: "https://github.com/robinthakur00/django-todo-app.git", branch: "dev"
            }
        }
        stage("Build Docker Image"){
            steps{
                sh "docker build -t django-todo-app ."
            }
        }
        stage("Login And Push to DockerHub"){
            steps{
                withCredentials([usernamePassword(credentialsId:"dockerHub",passwordVariable:"dockerHubPass",usernameVariable:"dockerHubUser")]){
                sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                sh "docker tag django-todo-app:latest ${env.dockerHubUser}/django-todo-app:latest"
                sh "docker push ${env.dockerHubUser}/django-todo-app:latest"
                }
            }
        }
        stage("Deploy the application"){
            steps{
                sh "docker-compose down && docker-compose up -d"
            }
        }
    }
}
