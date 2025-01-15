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
                dir('frontend\\ConsoleApp\\bin\\Debug\\net8.0') {
                    bat "ConsoleApp.exe"
                }

				
            }
        }
        stage('Test') {
            steps {
                echo "Test"
                
            }
        }
    }
}
