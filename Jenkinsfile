pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *') // Poll the SCM every 5 minutes
    }

    environment {
        TARGET_DIR = '/your/target/folder'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'develop', url: 'https://your-repo-url.git'
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
