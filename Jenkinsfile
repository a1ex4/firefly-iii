pipeline {
  agent any
  stages {
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