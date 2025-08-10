pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'master', url: 'https://github.com/Kaleakash/ci-cd-chaos-lab.git'
            }
        }

        stage('Build Docker Images') {
            steps {
                sh 'docker-compose build'
            }
        }

        stage('Deploy and Start Chaos') {
            steps {
                sh 'docker-compose up -d'
            }
        }

        stage('Verify App') {
            steps {
                sh 'curl -f http://localhost:5000'
            }
        }
    }
}
