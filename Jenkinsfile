pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    echo 'Cloning the EasyDevOps repository...'
                    // Verwijder de bestaande directory (indien aanwezig) en kloon opnieuw
                    bat '''
                        if exist TEST-DEVOPS (
                            rmdir /s /q TEST-DEVOPS
                        )
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
