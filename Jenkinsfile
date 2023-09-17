pipeline{
    agent {
        label 'php_agent'
    }

    environment {
        IMAGE_TAG = "Default"
        // CONTAINER_NAME = "BELIEVE"
        // APP_PORT = 8080             // Port on server       APP_PORT:CONTAINER_PORT
        // CONTAINER_PORT = 8080       // Port in container
    }

    stages {
        stage("Run containers") {
            steps {
                sh "docker-compose up -d"
            }
        }
    }
}
