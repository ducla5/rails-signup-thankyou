pipeline {
  agent {
    docker {
      image 'ruby:2.5.5-slim-stretch'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'bundle install'
      }
    }
  }
}