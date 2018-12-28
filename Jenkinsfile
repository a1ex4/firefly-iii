pipeline {
  agent any
  stages {
    stage('Sync repo') {
      steps {
        sh 'git fetch upstream'
        sh 'git checkout develop'
        sh 'git merge upstream/develop'
        sh 'git remote -v'
      }
    }
    stage('Build image') {
      steps {
        sh 'docker build -t testimage .'
      }
    }
  }
}