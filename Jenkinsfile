pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo "test"
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo "Build"
                bat "dir"
                dir('frontend') {
                    bat "dotnet build"
                }
            }
        }
        stage('Test') {
            steps {
                echo "Test"
                // Add your test commands here
            }
        }
    }
}

