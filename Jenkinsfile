pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('ckeckout') {
      steps {
        git(url: 'https://github.com/sandy-7assan/final-python', branch: 'main')
      }
    }

    stage('build') {
      steps {
        sh 'docker build -t test:$BUILD_ID .'
      }
    }

  }
}