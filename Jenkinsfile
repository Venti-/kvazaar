pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        dir(path: 'src') {
          sh 'make -j4'
        }
        
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