pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t myapp .'
            }
        }

        stage('Tag Docker Image') {
            steps {
                bat 'docker tag myapp sannidhi005/myapp:v1'
            }
        }

        stage('Docker Login') {
            steps {
                bat 'docker login -u sannidhi005 -p San@docker'
            }
        }

        stage('Push Image') {
            steps {
                bat 'docker push sannidhi005/myapp:v1'
            }
        }
    }
}
