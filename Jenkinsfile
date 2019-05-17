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
        sh 'bundle install'
      }
    }
    stage('Test') {
      steps {
        sh 'rspec  --format html --out rspec_results/results.html --format RspecJunitFormatter --out rspec_results/results.xml'
      }
    }
    stage('Deploy') {
      steps {
        input 'Are you sure about deploying new version ?'
      }
    }
  }
  post {
    always {
      junit 'rspec_results/*.xml'
    }
  }
}
