pipeline {
  agent any
  tools {nodejs "node-installation"}
  stages {
    stage('Git') {
      steps {
        git 'https://github.com/alek-wind/hello-world-nodejs'
	  }
    }
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }
    stage('Test') {
      steps {
        sh 'npm test'
      }
    }
    stage('Deploy') {
      steps {
        sh '/Users/alrodionov/Desktop/deploy/deploy.sh'
      }
    }
  }
}