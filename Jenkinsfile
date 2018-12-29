pipeline {
  agent any
  stages {
    stage('Sync repo') {
      steps {
        sh 'git fetch upstream'
        sh 'git checkout upstream/develop'
        sh 'git merge upstream/develop'
        sh 'git remote -v'
        sh 'git describe --tags'
        sh 'git rev-parse --short HEAD'
      }
    }
    stage('Build image') {
      steps {
        sh 'docker build -t testimage .'
      }
    }
  }
}