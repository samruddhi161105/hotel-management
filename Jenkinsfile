pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t hotel-app .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker stop hotel-app || exit 0'
                bat 'docker rm hotel-app || exit 0'
                bat 'docker run -d -p 3000:3000 --name hotel-app hotel-app'
            }
        }
    }
}