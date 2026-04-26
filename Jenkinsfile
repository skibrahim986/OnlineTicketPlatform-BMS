pipeline {
    agent any

    environment {
        IMAGE_NAME = "bms-node-app"
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f bms-container || true
                docker run -d -p 3000:3000 --name bms-container $IMAGE_NAME
                '''
            }
        }
    }

    post {
        success {
            echo "App deployed successfully!"
        }
        failure {
            echo "Pipeline failed!"
        }
    }
}
