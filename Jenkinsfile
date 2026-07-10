pipeline {
    agent {
        label 'slave-1'
    }

    stages {

        stage('Get Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/kasturisiri/02-war-project.git'
            }
        }

        stage('Check Environment') {
            steps {
                sh '''
                    echo "PATH=$PATH"
                    which java
                    java -version
                    which mvn
                    mvn -version
                '''
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
