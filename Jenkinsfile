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
    stage('Test') {
      steps {
        input 'Proceed to test?'
        sh 'make check'
      }
    }
    stage('Package') {
      steps {
        input 'Proceed to package?'
        archiveArtifacts(artifacts: 'src/kvazaar', onlyIfSuccessful: true)
      }
    }
  }
}
