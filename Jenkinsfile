pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/manjunath2703/DevOps-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t manjunath2703/devops-app .'
            }
        }

        stage('Docker Login') {
            steps {
                sh 'docker login -u manjunath2703 -p YOUR_PASSWORD'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push manjunath2703/devops-app'
            }
        }

        stage('Deploy using Ansible') {
            steps {
                sh 'ansible-playbook playbook.yml'
            }
        }

    }
}
