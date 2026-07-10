pipeline {
    agent any

    environment {
        PATH = "$PATH:/opt/apache-maven-3.6.3/bin"
    }

    stages {

        stage('Get Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/kasturisiri/02-war-project.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('Sonar-Server-9.9.8') {
                    sh 'mvn sonar:sonar'
                }
            }
        }

    }
}