pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                git 'https://github.com/FROZEN00003/MLGIT.git'
            }
        }

        stage('Docker Check') {
            steps {
                bat 'wsl -d Ubuntu -- docker --version'
                bat 'wsl -d Ubuntu -- docker ps'
            }
        }

        stage('Test') {
            steps {
                bat 'wsl -d Ubuntu -- docker build -t web-image-app .'
            }
        }

        stage('Deploy') {
            steps {
                bat 'wsl -d Ubuntu -- docker run -d -p 8090:80 web-image-app'
            }
        }
    }
}