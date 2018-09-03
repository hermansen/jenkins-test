pipeline {
    agent any

    stages {
        stage('checkout') {
                steps {
                    echo 'Building..'
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/hermansen/jenkins-test.git']]])
                    sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
                }
            }
        stage('Build') {
            steps {
                echo 'Building..'
                sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
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
