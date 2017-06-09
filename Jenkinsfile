pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''./autogen.sh'''
        sh './configure --disable-dynamic --enable-static'
        sh 'make -j4'
      }
    }
    input 'Proceed to test?'
    stage('Test') {
      steps {
        sh 'make check'
      }
    }
    input 'Proceed to package?'
    stage('Package') {
      steps {
        archiveArtifacts(artifacts: 'src/kvazaar', onlyIfSuccessful: true)
      }
    }
  }
}
