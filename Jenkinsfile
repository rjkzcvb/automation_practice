pipeline {
    agent any

    stages {
        stage('git checkout') {
            steps {
                checkout scm
            }
        }

        stage('unit-test') {
            steps {
                sh 'python3 test_app.py'
            }
        }

        stage('smoke-test') {
            steps {
                sh 'python3 app.py 2 3'
            }
        }
    }
}
