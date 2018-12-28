pipeline {
  agent any
  stages {
    stage('Add upstream') {
      steps {
        sh 'git remote -v'
        sh 'git remote add upstream https://github.com/firefly-iii/firefly-iii.git'
        sh 'git remote -v'
      }
    }
    stage('Change to dev') {
      steps {
        sh 'git checkout develop'
      }
    }
  }
}