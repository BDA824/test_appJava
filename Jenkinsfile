pipeline {
    agent any

    stages {
        stage('Check Workspace') {
            steps {
                script {
                    bat 'dir /s /b'
                }
            }
        }
        stage('Build') {
            steps {
                script {
                    bat 'javac src/Hello.java'
                    bat 'cd src ; jar cf Hello.jar Hello.class'
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