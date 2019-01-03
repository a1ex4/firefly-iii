pipeline {
  agent any
  stages {
    stage('Build image') {
      parallel {
        stage('Build develop image') {
          when {
            branch 'develop'
          }
          steps {
            sh 'docker build -t a1ex4/rpi-firefly-iii:develop .'
          }
        }
        stage('Build release imge') {
          when {
            branch 'master'
          }
          steps {
            sh 'echo \'we on master\''
            sh 'IMAGE_TAG=$(git describe --abbrev=0 --tags)'
            sh "docker build -t a1ex4/rpi-firefly-iii:$IMAGE_TAG ."
          }
        }
      }
    }
    stage('Echo image tag') {
      steps {
        sh 'echo $IMAGE_TAG'
      }
    }
  }
}
