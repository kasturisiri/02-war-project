pipeline {
    agent any

    environment {
        PATH = "${env.PATH}:/opt/apache-maven-3.9.10/bin"
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
    }
}
