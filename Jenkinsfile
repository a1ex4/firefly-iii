pipeline {
  agent any
  stages {
    stage('Set image tag') {
      parallel {
        stage('Set develop tag') {
          when {
            branch 'develop'
          }
          steps {
            sh 'echo \'we on develop\''
            sh 'IMAGE_TAG=\'develop\''
          }
        }
        stage('Set release tag') {
           when {
            branch 'master'
          }
          steps {
            sh 'echo \'we on master\''
            sh 'IMAGE_TAG=\'release\''
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
