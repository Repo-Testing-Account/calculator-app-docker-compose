pipeline {
    agent any
    environment {
        REGISTRY = 'localhost:5000'
        IMAGE_NAME = 'calculator'
        FULL_IMAGE_NAME = "${REGISTRY}/${IMAGE_NAME}:${env.BUILD_ID}.0"
    }
    stages {
        stage('Build Image') {
            steps {
                // Execute standard docker build
                sh "docker build -t ${FULL_IMAGE_NAME} ."
            }
        }
        stage('Push Image') {
            steps {
                // Execute standard docker push
                sh "docker push ${FULL_IMAGE_NAME}"
            }
        }
    }
}
