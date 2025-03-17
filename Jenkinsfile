pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'javac src/Hello.java'
                    sh 'cd src && jar cf Hello.jar src/Hello.class'
                }
            }
        }
        stage('Archive') {
            steps {
            archiveArtifacts artifacts: 'src/Hello.jar', fingerprint: true
            }
        }
    }
}