pipeline {
    agent any

    stages {
        stage('GIT') {
            steps {
                git branch: 'master',
                    changelog: false,
                    credentialsId: 'jenkins-github',
                    url: 'https://github.com/AymenMb2/devops.git'
            }
        }

        stage('MAVEN Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('sonarcube') {
                    sh 'mvn sonar:sonar'
                }
            }
        }
    }
}
