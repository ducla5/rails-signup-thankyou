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
        sh '''

bundle install

'''
      }
    }
    stage('Test') {
      steps {
        sh 'rspec .'
      }
    }
    stage('Deploy') {
      steps {
        input 'Are you sure about deploying new version ?'
      }
    }
  }
}