pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/sandy-7assan/final-python', branch: 'main', changelog: true, poll: true)
      }
    }

  }
}