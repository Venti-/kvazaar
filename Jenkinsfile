pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''./autogen.sh

'''
        sh './configure --disable-dynamic --enable-static'
        sh 'make -j4'
      }
    }
    stage('Test') {
      steps {
        sh 'make check'
      }
    }
    stage('Package') {
      steps {
        archiveArtifacts(artifacts: 'src/kvazaar', onlyIfSuccessful: true)
      }
    }
  }
}