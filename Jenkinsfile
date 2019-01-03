pipeline {
  agent any
  stages {
    stage('Set develop tag') {
      parallel {
        stage('Set develop tag') {
          when {
            branch 'develop'
          }
          steps {
            sh 'echo \'we on develop\''
            sh 'IMAGE_TAG=\'develop\''
            sh 'echo $IMAGE_TAG'
          }
        }
        stage('Test') {
          steps {
            sh 'echo \'test stage\''
          }
        }
      }
    }
    stage('Set release tag') {
      when {
        branch 'master'
      }
      steps {
        sh 'echo \'we on master\''
        sh 'IMAGE_TAG=\'master\''
        sh 'echo $IMAGE_TAG'
      }
    }
  }
}