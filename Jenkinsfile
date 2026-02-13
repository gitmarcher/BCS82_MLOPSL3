pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "gitmarcher/wine-quality-api"
        DOCKER_CREDENTIALS = "docker-token"
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/gitmarcher/BCS82_MLOPSL4.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                python3 -m venv venv
                . venv/bin/activate
                pip install -r requirements.txt
                '''
            }
        }
    }
}
