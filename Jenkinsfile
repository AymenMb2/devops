pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    changelog: false,
                    credentialsId: 'jenkins.github',
                    url: 'https://github.com/AymenMb2/devops.git'
            }
        }

        stage('Maven Build') {
            steps {
                dir('student-management') {
                    sh 'mvn clean package -DskipTests'
                }
            }
        }
    }
}
