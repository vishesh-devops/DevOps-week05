pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building application'
                sh 'chmod +x app.sh'
                sh './app.sh'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests'
                sh 'chmod +x test.sh'
                sh './test.sh'
            }
        }

        stage('Validation') {
            steps {
                echo 'Validating project files'
                sh 'test -f app.sh'
                sh 'test -f test.sh'
                echo 'Validation successful'
            }
        }
    }
}
