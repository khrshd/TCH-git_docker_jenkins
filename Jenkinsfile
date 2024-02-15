pipeline {
    agent any 
    stages {
        stage('Pull Docker image') {
            steps {
                sh 'sudo docker run hello-world:latest'
                sh 'sudo docker compose build'
            }
        }
        stage('Docker test') {            
            steps {
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