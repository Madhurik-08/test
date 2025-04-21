pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "sample-node-app"
        DOCKER_TAG = "latest"
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/your-repo/sample-node-app.git' 
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
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
