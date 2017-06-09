pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'make -j2'
      }
    }
    stage('test') {
      steps {
        sh 'make test'
      }
    }
  }
}