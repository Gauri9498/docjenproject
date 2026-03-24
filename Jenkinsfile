pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/USERNAME/devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-website .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f website || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d -p 80:80 --name website my-website'
            }
        }
    }
}
