pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    bat 'javac src/Hello.java'
                    bat 'cd src ; jar cf Hello.jar Hello.class'
                }
            }
        }
        stage('Check Workspace') {
            script{
                steps {
                    bat 'dir /s /b'
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