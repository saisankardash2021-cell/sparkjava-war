pipeline {
    agent any

    environment {
        PATH = "/opt/maven/bin:${env.PATH}"
    }

    stages {

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('SonarQube Analysis') {
            environment {
                scannerHome = tool 'SonarQube-Scanner'
            }

            steps {
                withSonarQubeEnv('Saitech01-Saitech01_Project1-Server') {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }

    }
}
