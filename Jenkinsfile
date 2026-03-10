pipeline {
agent any

environment {
    DOCKER_IMAGE = "manjunath2703/devops-app"
}

stages {

    stage('Build Docker Image') {
        steps {
            sh 'docker build -t $DOCKER_IMAGE .'
        }
    }

    stage('Docker Login') {
        steps {
            sh 'echo "YOUR_DOCKER_PASSWORD" | docker login -u manjunath2703 --password-stdin'
        }
    }

    stage('Push Docker Image') {
        steps {
            sh 'docker push $DOCKER_IMAGE'
        }
    }

    stage('Deploy using Ansible') {
        steps {
            sh 'ansible-playbook playbook.yml'
        }
    }

}

}
