pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'javac src/Hello.java'
                sh 'cd src && jar cf Hello.jar sample/Hello.class'
            }
        }
        stage('Archive') {
            steps {
            archiveArtifacts artifacts: 'src/Hello.jar', fingerprint: true
            }
        }
    }
}