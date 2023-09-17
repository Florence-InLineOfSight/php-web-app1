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
        stage("Backup and Deploy") {
            steps {
                sh "docker-compose build"
                sh "docker-compose up -d"
                sh "docker tag php-web-app1_www:latest florenceomoruyi/php-web-app1:${env.IMAGE_TAG}"
                sh "docker push florenceomoruyi/php-web-app1:${env.IMAGE_TAG}"
            }
        }
    }
}

/*
Delete the old image(s)
Build the new image
Delete the old container
Run the new container(s): docker-compose up -d
Push new image to dockerhub
*/

