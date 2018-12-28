pipeline {
  agent {
    dockerfile {
      filename 'Dockerfile'
    }

  }
  stages {
    stage('Sync repo') {
      steps {
        svn(url: 'https://ci.a1ex.space/blue/rest/organizations/jenkins/scm/git/organizations/ff/repositories/ff/?apiUrl=https://github.com/firefly-iii/firefly-iii.git', poll: true)
      }
    }
  }
}