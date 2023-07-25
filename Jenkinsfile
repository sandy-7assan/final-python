pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/sandy-7assan/final-python', branch: 'main', changelog: true, poll: true)
      }
    }

    stage('build') {
      steps {
        sh 'docker build -t test1:$BUILD_ID .'
      }
    }

    stage('run & test') {
      steps {
        sh '''docker run --name testing -d -p 5000:5000 test1:$BUILD_ID
'''
        sleep 3
        sh 'curl localhost:8080'
        sh 'docker stop testing && docker rm testing'
      }
    }

  }
}