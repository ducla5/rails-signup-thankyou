pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'ruby:2.5.5-stretch'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'sudo apt-get install build-essential'
        sh '''

bundle install

'''
      }
    }
  }
}