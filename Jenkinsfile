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
        sh 'npm audit --level critical'
        script {
          if (manager.logContains('.*glob-parent before 5.1.2 .*')) {
            error("Build failed because of this and that..")    
          }
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