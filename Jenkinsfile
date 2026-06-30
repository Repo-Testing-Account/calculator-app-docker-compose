pipeline {
    agent any
    environment {
        // You can keep this as a local tag or change to your Docker Hub username
        IMAGE_NAME = 'calculator'
        FULL_IMAGE_NAME = "${IMAGE_NAME}:${env.BUILD_ID}.0"
    }
    stages {
        stage('Build Image') {
            steps {
                // Executes the Docker build command
                sh "docker build -t ${FULL_IMAGE_NAME} ."
            }
        }
    }
}
