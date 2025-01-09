pipeline {
    agent any

    stages {
        stage('Setup Environment') {
            steps {
                script {
                    echo 'Updating package list and installing dependencies...'
                    // Update package list en installeer Git
                    sh 'sudo apt update'
                    sh 'sudo apt install -y git'
                }
            }
        }

        stage('Install .NET SDK 8') {
            steps {
                script {
                    echo 'Installing .NET SDK 8...'
                    // Download en installeer de .NET SDK
                    sh 'wget https://dotnet.microsoft.com/download/dotnet/scripts/v1/dotnet-install.sh'
                    sh 'chmod +x dotnet-install.sh'
                    sh './dotnet-install.sh --version 8.0.100'
                }
            }
        }

        stage('Clone Repository') {
            steps {
                script {
                    echo 'Cloning the EasyDevOps repository...'
                    // Clone de repository
                    sh 'git clone https://github.com/GiovanniVanDijk/TEST-DEVOPS'
                }
            }
        }

        stage('Run Application') {
            steps {
                script {
                    echo 'Running the EasyDevOps application...'
                    // Ga naar de frontend directory en start de applicatie
                    sh 'cd TEST-DEVOPS/frontend && dotnet run'
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed!'
        }
        success {
            echo 'Pipeline ran successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
