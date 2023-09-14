pipeline {
    agent {
        label 'docker-deployment'
    }

    stages {
        stage('Delete old Images and Containers') {
            steps {
                //Delete present images and running containers
                sh 'docker stop php-web-app_www_1 && docker rm -f php-web-app_www_1 && docker rmi -f php-web-app_www:latest'
                // sh 'docker stop php-web-app_phpmyadmin_1 && docker rm -f php-web-app_phpmyadmin_1 && docker rmi -f phpmyadmin/phpmyadmin:latest'
                // sh 'docker stop php-web-app_db_1 && docker rm -f php-web-app_db_1 && docker rmi -f mysql:5.7.28'
            }
        }
        
        stage('Build and Deploy Using Docker-compose') {
            steps {
                sh 'docker-compose up -d'
                sh 'docker login -u "eufresia" -p "ngum677693061"'
                sh 'docker tag php-web-app_www:latest eufresia/ngum-php-web-app:1.0.3'
                sh 'docker push eufresia/ngum-php-web-app:1.0.3'
            }
        }
    }
}
