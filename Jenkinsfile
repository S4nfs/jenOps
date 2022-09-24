pipeline {
  agent any
  stages {
    stage('checkout to branch') {
      steps {
        git(url: 'https://github.com/S4nfs/jenOps', branch: 'pipeline3')
      }
    }

    stage('node modules install') {
      steps {
        sh 'npm i'
      }
    }

    stage('build docker image') {
      steps {
        sh 'docker build . -t jenOps by S4nfs'
      }
    }

    stage('TAG AND PUSH') {
      steps {
        sh 'docker push s4nfs/jenops'
      }
    }

  }
}