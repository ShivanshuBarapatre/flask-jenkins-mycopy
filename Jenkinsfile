pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git 'https://github.com/ShivanshuBarapatre/flask-jenkins-mycopy.git'
            }
        }

        stage('Install Dependencies') {
            agent {
                docker {
                    image 'python:3.10'
                }
            }
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            agent {
                docker {
                    image 'python:3.10'
                }
            }
            steps {
                sh 'echo "No tests yet, skipping..."'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 flask-app'
            }
        }
    }
}

