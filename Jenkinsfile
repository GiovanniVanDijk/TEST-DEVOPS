pipeline {
    agent any
    
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
