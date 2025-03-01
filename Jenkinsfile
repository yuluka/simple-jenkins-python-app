pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/yuluka/simple-jenkins-python-app.git'
            }
        }
        stage('Setup Python') {
            steps {
                sh '''
                python -m venv venv
                . venv/bin/activate
                pip install -r requirements.txt
                '''
            }
        }
        stage('Run Tests') {
            steps {
                sh '''
                . venv/bin/activate
                pytest --junitxml=test-results.xml
                '''
            }
        }
    }
}
