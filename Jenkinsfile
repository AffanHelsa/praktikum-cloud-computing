pipeline {
    agent any

    environment {
        // Menambahkan folder Docker CLI ke PATH khusus di Jenkins pipeline
        PATH = "C:\\Program Files\\Docker\\Docker\\resources\\bin;${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t affanhelsa/simple-app:5 .'
            }
        }
        stage('Push Docker Image') {
            steps {
                bat 'docker push affanhelsa/simple-app:5'
            }
        }
    }
    post {
        always {
            echo 'Selesai build'
        }
    }
}
