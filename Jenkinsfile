pipeline {
  agent any
  stages {
    stage('Build develop image') {
      when {
        branch 'develop'
      }
      steps {
        sh 'docker build -t a1ex4/rpi-firefly-iii:develop .'
      }
    }
    stage('Push develop image') {
      when {
        branch 'develop'
      }
      steps {
        sh 'docker push a1ex4/rpi-firefly-iii:develop'
      }
    }
    stage('Build release image') {
      when {
        branch 'master'
      }
      steps {
        sh 'docker build -t a1ex4/rpi-firefly-iii:$(git describe --abbrev=0 --tags) -t a1ex4/rpi-firefly-iii:latest .'
      }
    }
    stage('Push version tagged image') {
      when {
        branch 'master'
      }
      steps {
        sh 'docker push a1ex4/rpi-firefly-iii:$(git describe --abbrev=0 --tags)'
      }
    }
    stage('Push latest tagged image') {
      when {
        branch 'master'
      }
      steps {
        sh 'docker push a1ex4/rpi-firefly-iii:latest'
      }
    }
  }
}