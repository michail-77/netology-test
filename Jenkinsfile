pipeline {
  agent any
  stages {
    stage('Checkout Scm') {
      steps {
        git 'https://github.com/michail-77/netology-test/'
      }
    }

    stage('Shell script 0') {
      steps {
        sh '/usr/local/go/bin/go test .'
      }
    }

    stage('Shell script 1') {
      steps {
        sh 'docker build . -t ubuntu-bionic:8082/freestyle:test'
      }
    }
    stage('Shell script 2') {
      steps {
        sh 'docker login ubuntu-bionic:8082 -u admin -p admin && docker push ubuntu-bionic:8082/freestyle:test && docker logout'
      }
    }
  }
}