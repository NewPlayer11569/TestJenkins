pipeline {
    agent any

    environment {
        SONAR_SERVER_URL = 'http://192.168.56.123:30725'
        SONAR_TOKEN = 'sqa_242c55737a436b4510bfa80050944f88544391ae'
        PROJECT_KEY = 'Test'
    }

    stages {

        stage('SonarQube Analysis') {
            steps {
                script {
                    def scannerHome = tool 'SonarQubeScannerMSBuild'
                    bat """
                        "${scannerHome}\\SonarScanner.MSBuild.exe" begin /k:"${PROJECT_KEY}" /d:sonar.host.url=${SONAR_SERVER_URL} /d:sonar.login=${SONAR_TOKEN}
                        dotnet build YourSolution.sln
                        "${scannerHome}\\SonarScanner.MSBuild.exe" end /d:sonar.login=${SONAR_TOKEN}
                    """
                }
            }
        }
    }
}
