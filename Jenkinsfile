pipeline {
    agent any
    environment {
        DOCKER_CREDENTIALS_ID = '14b1cb9a-a289-49a5-89b4-24eb0723647e'
        IMAGE_TAG = 'wahajrahman/mlops-assignment-1:latest'
    }
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build(IMAGE_TAG)
                }
            }
        }
        stage('Push Image to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', DOCKER_CREDENTIALS_ID) {
                        docker.image(IMAGE_TAG).push()
                    }
                }
            }
        }
    }
}
