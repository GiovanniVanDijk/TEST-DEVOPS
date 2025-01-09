pipeline {
    agent any

    stages {
        stage('Clone Repository') {
     steps {
        script {
            echo 'Cloning or updating the EasyDevOps repository...'
            bat '''
                if exist TEST-DEVOPS (
                    cd TEST-DEVOPS
                    git pull origin main
                ) else (
                    git clone https://github.com/GiovanniVanDijk/TEST-DEVOPS.git
                )
            '''
                }
            }
        }

        stage('Run Application') {
            steps {
                script {
                    echo 'Running the EasyDevOps application...'
                    // Ga naar de frontend directory en start de applicatie
                    dir('TEST-DEVOPS/frontend') {
                        sh 'dotnet run'
                }
            }
        }
    }
}
}
