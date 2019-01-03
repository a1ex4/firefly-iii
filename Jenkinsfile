pipeline {
  agent any
  stages {
    stage('Build and push image') {
      parallel {
        stage('DEVELOP') {
          when {
            branch 'develop'
          }
          stages {
            stage('Build develop image') {
              steps {
                sh 'docker build -t a1ex4/rpi-firefly-iii:develop .'
              }
            }
            stage('Push develop image') {
              steps {
                sh 'docker push a1ex4/rpi-firefly-iii:develop'
              }
            }
          }
        }
        stage('RELEASE') {
          when {
            branch 'master'
          }
          stages {
            stage('Build release image') {
              steps {
                sh 'docker build -t a1ex4/rpi-firefly-iii:$(git describe --abbrev=0 --tags) -t a1ex4/rpi-firefly-iii:latest  .'
                }
              }
            stage('Push version tagged image') {
              steps {
                sh 'docker build -t a1ex4/rpi-firefly-iii:$(git describe --abbrev=0 --tags) -t a1ex4/rpi-firefly-iii:latest  .'
              }
            }
            stage('Push latest tagged image') {
              steps {
                sh 'docker push a1ex4/rpi-firefly-iii:latest'
              }
            }
          }
        }
      }
    }
  }
}
