pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // This pulls the code from your GitHub repository
                checkout scm
            }
        }

        stage('Build Backend') {
            steps {
                // Builds the Docker image for the C++ backend
                sh 'docker build -t backend-app ./backend'
            }
        }

        stage('Deploy NGINX') {
        steps {
            sh 'docker pull nginx'
            sh 'docker rm -f lab-nginx || true'
            sh "docker run -d --name lab-nginx -p 80:80 -v ${WORKSPACE}/nginx:/etc/nginx/conf.d nginx"
        }
    }
    }
}