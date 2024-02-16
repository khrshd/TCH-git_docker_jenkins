pipeline {
    agent any 
    stages {
        stage('Cleaning up previous docker builds, images and containers'){
            steps {
                sh 'sudo docker stop $(sudo docker ps -a -q)'
                sh 'sudo docker rm $(sudo docker ps -a -q)'
                sh 'sudo docker rmi $(sudo docker images -a -q)'
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
                sh 'docker run -d --name my-httpd-cont3 -p 5003:80 my-apache:latest'
                sh 'curl localhost:5003'
            }
        }
        stage('Test techs') {
            steps {
                sh 'docker --version && git --version && jenkins --version'
            }
        }
        stage('Deploy & Cleanup') {
            steps {
                sh 'ls -l && whoami && hostnamectl'
                sh 'sudo docker stop $(sudo docker ps -a -q)'
                sh 'sudo docker rm $(sudo docker ps -a -q)'
                sh 'sudo docker rmi $(sudo docker images -a -q)'
            }
        }
    }
}