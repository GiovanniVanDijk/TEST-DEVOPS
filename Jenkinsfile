pipeline {
    agent any

    stages {
        stage('Setup Environment') {
            steps {
                script {
                    echo 'Updating package list and installing dependencies...'
                    // Update package list en installeer Git via SSH
                    sh '''
                        sshpass -p "Welkom01!" ssh -o StrictHostKeyChecking=no giovanni@192.169.36.148 "
                            sudo apt update &&
                            sudo apt install -y git
                        "
                    '''
                }
            }
        }

        stage('Install .NET SDK 8') {
            steps {
                script {
                    echo 'Installing .NET SDK 8...'
                    // Installeer de .NET SDK via SSH
                    sh '''
                        sshpass -p "Welkom01!" ssh -o StrictHostKeyChecking=no giovanni@192.169.36.148 "
                            wget https://dotnet.microsoft.com/download/dotnet/scripts/v1/dotnet-install.sh &&
                            chmod +x dotnet-install.sh &&
                            ./dotnet-install.sh --version 8.0.100
                        "
                    '''
                }
            }
        }

        stage('Clone Repository') {
            steps {
                script {
                    echo 'Cloning the EasyDevOps repository...'
                    // Clone de repository via SSH
                    sh '''
                        sshpass -p "Welkom01!" ssh -o StrictHostKeyChecking=no giovanni@192.169.36.148 "
                            git clone https://github.com/GiovanniVanDijk/TEST-DEVOPS.git
                        "
                    '''
                }
            }
        }

        stage('Run Application') {
            steps {
                script {
                    echo 'Running the EasyDevOps application...'
                    // Ga naar de frontend directory en start de applicatie via SSH
                    sh '''
                        sshpass -p "Welkom01!" ssh -o StrictHostKeyChecking=no giovanni@192.169.36.148 "
                            cd TEST-DEVOPS/frontend &&
                            dotnet run
                        "
                    '''
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
