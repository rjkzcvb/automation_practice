pipeline {
    agent any

    stages {
        stage('git checkout') {
            steps {
                checkout scm
            }
        }

        stage('setup python') {
            steps {
                sh '''
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install pytest
                '''
            }
        }

        stage('unit-test') {
            steps {
                sh '''
                    . venv/bin/activate
                    python test_app.py
                '''
            }
        }

        stage('smoke-test') {
            steps {
                sh '''
                    . venv/bin/activate
                    python app.py 2 3
                '''
            }
        }
    }
}
