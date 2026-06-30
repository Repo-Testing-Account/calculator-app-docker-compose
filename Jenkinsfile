pipeline {
    agent any
    environment {
        // Define your registry address
        REGISTRY = 'localhost:5000'
        IMAGE_NAME = 'calculator'
        FULL_IMAGE_NAME = "${REGISTRY}/${IMAGE_NAME}:${env.BUILD_ID}"
    }
    stages {
        stage('Build Image') {
            steps {
                script {
                    // This builds the image from the Dockerfile in the current directory
                    app = docker.build("${FULL_IMAGE_NAME}")
                }
            }
        }
        stage('Push Image') {
            steps {
                script {
                    // Pushing to local registry
                    // Note: If your local registry is insecure (no HTTPS), 
                    // ensure your Docker daemon has it in 'insecure-registries'
                    app.push()
                }
            }
        }
    }
}
