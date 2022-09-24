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
        sh 'docker build -t jenops .'
      }
    }

    stage('TAG AND PUSH') {
      parallel {
        stage('TAG AND PUSH') {
          steps {
            sh 'docker build -t jenops .'
            sh 'docker image tag jenops s4nfs/jenops:latest'
          }
        }

        stage('push') {
          steps {
            sh 'docker push s4nfs/jenops:latest'
          }
        }

      }
    }

  }
}