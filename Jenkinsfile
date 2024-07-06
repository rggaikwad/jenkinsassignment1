pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *') // Poll the SCM every 5 minutes
    }

    environment {
        TARGET_DIR = '/home/ubuntu/jenkinsassignment1'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'develop', url: 'https://github.com/rggaikwad/jenkinsassignment1.git'
            }
        }
        
        stage('Deploy') {
            steps {
                script {
                    sh "mkdir -p ${TARGET_DIR}"
                    sh "cp -r . ${TARGET_DIR}"
                }
            }
        }
    }
}
