pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/Gauri9498/docjenproject.git'
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
                sh 'docker run -d -p 8081:80 --name website my-website'
            }
        }
    }
}
