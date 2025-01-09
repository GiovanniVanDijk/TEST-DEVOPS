pipeline {
    agent {
        label 'windows' // Zorg ervoor dat de Jenkins-agent op de Windows-server draait
    }

    stages {
        stage('Setup Environment') {
            steps {
                script {
                    echo 'Setting up environment on Windows Server...'
                    // Update omgeving en installeer dependencies
                    bat '''
                        choco install git -y
                        choco install dotnet-sdk -y
                    '''
                }
            }
        }

        stage('Clone Repository') {
            steps {
                script {
                    echo 'Cloning the EasyDevOps repository...'
                    // Clone de repository
                    bat '''
                        git clone https://github.com/GiovanniVanDijk/TEST-DEVOPS.git
                    '''
                }
            }
        }

        stage('Run Application') {
            steps {
                script {
                    echo 'Running the EasyDevOps application...'
                    // Ga naar de frontend directory en start de applicatie
                    bat '''
                        cd TEST-DEVOPS\\frontend
                        dotnet run
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
