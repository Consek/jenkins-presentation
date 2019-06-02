pipeline {
  agent {
    docker {
      image 'centos:7'
    }

  }
  stages {
    stage('First branch') {
      parallel {
        stage('First branch') {
          steps {
            sh 'echo "First branch"'
          }
        }
        stage('Second branch') {
          steps {
            sh '''echo "Second branch"
'''
          }
        }
      }
    }
  }
}