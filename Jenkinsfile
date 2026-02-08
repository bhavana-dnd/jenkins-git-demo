pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/bhavana-dnd/jenkins-git-demo.git'
            }
        }

        stage('Build') {
            steps {
                bat 'javac HelloCI.java'
            }
        }

        stage('Test') {
            steps {
                bat 'java HelloCI'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: '*.class'
            echo 'CI PIPELINE SUCCESSFUL'
        }
        failure {
            echo 'CI PIPELINE FAILED'
        }
    }
}
