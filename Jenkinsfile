pipeline {
  agent any
  stages {
    stage('Sync repo') {
      steps {
        sh 'git fetch upstream'
        sh 'git checkout develop'
        sh 'git merge upstream/develop'
      }
    }
    stage('Change to dev') {
      steps {
        sh 'git branch'
        git(url: 'https://github.com/a1ex4/firefly-iii', branch: 'develop')
      }
    }
  }
}