pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Vishal758168/Jenkins-Project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mywebsite .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker stop mywebsite || true'
                sh 'docker rm mywebsite || true'
                sh 'docker run -d -p 80:80 --name mywebsite mywebsite'
            }
        }
    }
}

