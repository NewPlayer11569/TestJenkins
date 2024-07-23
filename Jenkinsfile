pipeline {
    agent any

    environment {
        SONAR_SERVER_URL = 'http://192.168.56.123:30725'
        SONAR_TOKEN = 'sqa_242c55737a436b4510bfa80050944f88544391ae'
        PROJECT_KEY = 'Test'
    }

    stages {

        stage('Hello') {
            steps {
                script {
                    sh """
                        whoami
                    """
                }
            }
        }
    }
}
