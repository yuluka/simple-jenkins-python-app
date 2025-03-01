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
                python3 -m venv venv
                bash -c "source venv/bin/activate && pip install -r requirements.txt"
                '''
            }
        }
        stage('Run Tests') {
            steps {
                sh '''
                bash -c "source venv/bin/activate && pytest --junitxml=test-results.xml"
                '''
            }
        }
    }
}
