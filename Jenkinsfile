pipeline {
    agent any
    
    environment {
        DOCKER_IMAGE = "sample-node-app"
        DOCKER_TAG = "latest"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch:'main', url:'https://github.com/Madhurik-08/test' 
            }
        }
    
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("${DOCKER_IMAGE}:${DOCKER_TAG}")
                }
            }
        }

    }

    post {
        always {
            cleanWs()
        }
    }
}
