pipeline {
  agent {
    node {
      label 'Build'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t myCiImage .'
      }
    }
  }
}