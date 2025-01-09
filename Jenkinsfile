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
                    bat '''
                        "C:\\Program Files\\Git\\bin\\bash.exe" -c "cd C:\Users\Giovd\AppData\Local\Jenkins\.jenkins\workspace\github\Frontend && dotnet run"
                    '''
                }
            }
        }
    }
}

