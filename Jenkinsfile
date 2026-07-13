pipeline {
    agent {
        label 'master'
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
