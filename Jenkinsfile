pipeline {
    agent any

    stages {
        stage('Checkout') {
                steps {
                    echo 'Building..'
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/hermansen/jenkins-test.git']]])
                }
            }
        stage('Build') {
            steps {
                echo 'Building..'
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
