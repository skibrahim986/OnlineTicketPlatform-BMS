pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/skibrahim986/bms-devops-project.git'
            }
        }

        stage('Build') {
            steps {
                echo "Build started..."
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
            }
        }
    }
}
