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

    stage('run & test') {
      steps {
        sh 'docker run --name test -d -p 5000:5000 test:$BUILD_ID'
        sleep 3
        sh 'curl localhost:5000/api/doc'
        sh 'docker stop test && docker rm test'
      }
    }

  }
}