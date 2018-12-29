pipeline {
  agent any
  stages {
    stage('Sync repo') {
      steps {
        sh 'git fetch upstream'
        sh 'git checkout upstream/develop'
        sh 'git merge upstream/develop'
      }
    }
    stage('Build image') {
      steps {
        sh 'docker build -t a1ex4/rpi-firefly-iii:dev-${git describe --tags} .'
      }
    }
  }
}