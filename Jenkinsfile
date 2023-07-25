pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('ckeckout') {
      steps {
        git(url: 'https://github.com/sandy-7assan/final-python', branch: 'main', changelog: true, poll: true)
      }
    }

  }
}