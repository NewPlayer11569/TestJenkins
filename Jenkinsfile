pipeline {
    agent any

    environment {
        SONAR_SERVER_URL = 'http://192.168.56.123:30725'
        SONAR_TOKEN = 'sqa_242c55737a436b4510bfa80050944f88544391ae'
        PROJECT_KEY = 'Test'
        PATH = "${env.PATH}:${env.HOME}/.dotnet/tools"
    }

    stages {

        stage('SonarQube Analysis') {
            steps {
                script {
                    sh """
                        dotnet sonarscanner begin /k:"${PROJECT_KEY}" /d:sonar.host.url=${SONAR_SERVER_URL} /d:sonar.login=${SONAR_TOKEN}
                        dotnet build
                        dotnet sonarscanner end /d:sonar.token=${SONAR_TOKEN}
                    """
                }
            }
        }
    }
}
