pipeline {
  agent any
  stages {
    stage('Sync repo') {
      steps {
        sh 'git fetch upstream'
        sh 'git checkout upstream/develop'
      }
    }
    stage('Build image') {
      steps {
        sh 'docker build -t a1ex4/rpi-firefly-iii:develop .'
      }
    }
    stage('Upload image') {
      steps {
        sh 'docker push a1ex4/rpi-firefly-iii:develop'
      }
    }
  }
}