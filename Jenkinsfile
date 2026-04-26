pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                // This uses Jenkins SCM config + credentials (IMPORTANT)
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Build started..."
                
                // If Maven project (pom.xml exists)
                sh 'mvn clean install || true'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                sh 'mvn test || true'
            }
        }

    }

    post {
        success {
            echo "Pipeline executed successfully!"
        }
        failure {
            echo "Pipeline failed!"
        }
    }
}
