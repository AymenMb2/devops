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
                dir('student-management') {
                    sh 'mvn clean'
                }
            }
        }
        stage('MVN COMPILE') {
            steps {
                dir('student-management') {
                    sh 'mvn compile'
                }
            }
        }
        stage('MVN SONARQUBE') {
            steps {
                dir('student-management') {
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
}
