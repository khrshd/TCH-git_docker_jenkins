pipeline {
    agent any 
    stages {
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