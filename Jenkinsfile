pipeline {
    agent any 
    stages {
        stage('Cleaning up previous docker builds, images and containers'){
            steps {
                sh 'docker stop $(docker ps -a -q)'
                sh 'docker rm $(docker ps -a -q)'
                sh 'docker images prune'
                sh 'docker prune -a'
            }
        }
        stage('Pull Docker image') {
            steps {
                sh 'sudo docker run hello-world:latest'
                sh 'docker ps -a && docker images'                
            }
        }
        stage('Dockerfile test') {            
            steps {
                sh 'sudo docker build -t my-apache:latest .'
                sh 'docker ps -a && docker images'
                sh 'docker run -d --name my-httpd-cont -p 5001:80 my-apache:latest'
                sh 'curl localhost:5002'
            }
        }
        stage('Test techs') {
            steps {
                sh 'docker --version && git --version && jenkins --version'
            }
        }
        stage('Deploy') {
            steps {
                sh 'ls -l && whoami && hostnamectl'
            }
        }
    }
}