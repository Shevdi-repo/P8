pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Shevdi-repo/P8.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-php-app .'
            }
        }

        stage('Deploy Docker Container') {
            steps {
                sh 'docker rm -f my-php-app-container || true'
                sh 'docker run -d --name my-php-app-container -p 8080:80 my-php-app'
            }
        }
    }
}
