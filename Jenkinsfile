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
    stage('Audit') {
      steps {
        sh 'npm audit || exit 0'
        script {
          //if (manager.logContains('.*code execution via the.*')) {
            sh 'echo \'In if statement\''
            error("Build failed because of this and that..")    
          //}
        }
      }
    }
    stage('Deploy') {
      steps {
        sh '/Users/alrodionov/Desktop/deploy/deploy.sh'
      }
    }
  }
}