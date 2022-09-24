pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
        git(branch: 'pipeline3', url: 'https://github.com/S4nfs/jenOps')
      }
    }

    stage('node modules') {
      steps {
        sh 'npm i'
      }
    }

  }
}