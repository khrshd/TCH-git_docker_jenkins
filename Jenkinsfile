pipeline {
    agent { docker { image 'hello-world:latest' } }
    stages {
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