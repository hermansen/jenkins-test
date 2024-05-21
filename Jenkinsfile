pipeline {
    agent any

    parameters {
        string(name: 'VERSION_TAG', defaultValue: '', description: 'Tag to publish')
    }

    stages {
        stage('Build') {
            steps {
                sh "./gradlew assembleDebug"
            }
        }
        stage('Upload') {
            steps {
                withCredentials([aws(accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'jenkins-aws', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY')]) {
                    sh "./gradlew filesUpload"
                }
            }
        }
    }
}