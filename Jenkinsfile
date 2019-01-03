pipeline {
  agent any
  stages {
    stage('Build release image') {
      steps {
        sh 'git describe --abbrev=0 --tags'
      }
    }
  }
}