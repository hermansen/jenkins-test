pipeline {
    agent any
    def mvnHome
    stages {
        stage('Checkout') {
                git 'https://github.com/hermansen/jenkins-test.git']]])
                mvnHome = tool 'M3'
            }
        stage('Build') {
            script {
                    sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
