pipeline {
  agent any
  stages {
    stage('Add upstream') {
      steps {
        sh 'git remote -v'
      }
    }
    stage('Change to dev') {
      steps {
        sh 'git branch'
        sh 'git checkout develop'
        git(url: 'https://github.com/a1ex4/firefly-iii', branch: 'develop')
      }
    }
  }
}