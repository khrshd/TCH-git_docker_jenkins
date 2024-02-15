pipeline {
    agent any
    stages {
        stage('Docker') {
            docker { image 'hellow-world:latest' }
            steps {
                sh 'docker ps -a && docker images'
            }
        }
        stage('Test') {
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