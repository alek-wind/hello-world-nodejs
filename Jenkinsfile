pipeline {
    agent { dockerfile true }
    stages {
        stage('Test') {
            steps {
                // sh 'yarn --version'

                sh 'node --version'
                sh 'svn --version'
            }
        }
    }
}