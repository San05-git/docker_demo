pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t myapp .'
            }
        }

        stage('Tag Image') {
            steps {
                bat 'docker tag myapp sannidhi005/myapp:v1'
            }
        }

        stage('Login to Docker Hub') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'docker_credentials_d1',
                    usernameVariable: 'USER',
                    passwordVariable: 'PASS'
                )]) {
                    bat 'echo %PASS% | docker login -u %USER% --password-stdin'
                }
            }
        }

        stage('Push Image') {
            steps {
                bat 'docker push sannidhi005/myapp:v1'
            }
        }
    }
}
