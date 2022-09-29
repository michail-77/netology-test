pipeline {
  agent any
  stages {
    stage('Git') {
      steps {
        git 'https://github.com/michail-77/netology-test/'
      }
    }

    stage('Test') {
      steps {
        sh '/usr/local/go/bin/go test .'
      }
    }

    stage('Build') {
      steps {
        sh 'RUN CGO_ENABLED=0 GOOS=linux go build -a -buildvcs=false -installsuffix nocgo -o /app .'
      }
    }
    stage('Push') {
      steps {
        sh 'docker login ubuntu-bionic:8082 -u admin -p admin && docker push ubuntu-bionic:8082/go:test && docker logout'
      }
    }
  }
}