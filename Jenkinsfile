pipeline {
  agent any
  stages {
    stage('Checkout Scm') {
      steps {
        git 'https://github.com/michail-77/netology-test'
      }
    }

    stage('Shell script 0') {
      steps {
        sh 'go test .'
      }
    }

    stage('Shell script 1') {
      steps {
        sh 'docker build . -t ubuntu-bionic:8082/freestyle:test'
      }
    }

  }
}