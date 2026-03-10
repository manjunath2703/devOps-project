pipeline {
agent any

environment {
    DOCKER_IMAGE = "manjunathbm2003/devops-app"
}

stages {

    stage('Build Docker Image') {
        steps {
            sh 'docker build -t $DOCKER_IMAGE .'
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
