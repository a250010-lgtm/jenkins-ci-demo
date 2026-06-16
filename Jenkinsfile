pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Cloning GitHub repo'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Compiling Java code'
                bat 'javac App.java TestApp.java'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests'
                bat 'java App'
                bat 'java TestApp'
            }
        }
    }

    post {
        success {
            echo 'BUILD SUCCESSFUL'
        }
        failure {
            echo 'BUILD FAILED'
        }
    }
}