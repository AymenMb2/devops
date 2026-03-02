pipeline {
    agent any
    stages {
        stage('GIT') {
            steps {
                git branch: 'main', url: 'https://github.com/AymenMb2/devops.git'
            }
        }
        stage('MVN CLEAN') {
            steps {
                sh 'mvn clean'
            }
        }
        stage('MVN COMPILE') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('MVN SONARQUBE') {
            steps {
                sh '''
                    mvn sonar:sonar \
                    -Dsonar.projectKey=valid \
                    -Dsonar.host.url=http://192.168.153.137:9000 \
                    -Dsonar.login=d1f8a2118778130e4a9faa5a878d5429fbf2608a
                '''
            }
        }
    }
}
