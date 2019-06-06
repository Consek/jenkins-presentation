pipeline{
  agent none
  options {
    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '2')
    timestamps()
  }
  environment {
    DEBUG = "1"
  }
  stages{
    stage('Build Linux Fedora 29') {
      parallel {
        stage('Fedora 29') {
          stages {
            stage('Build'){
              steps{
                echo 'Build'
              }
            }
            stage('Unit Test'){
              steps{
                echo 'Unit Test'
              }
            }
          }
        }
        stage('Ubuntu 18.04'){
          steps{
            echo 'Build'
          }
          when {
            branch 'master'
          }
        }
      }
    }
    stage('Integration Tests'){
      steps{
        echo 'Integration Tests'
      }
    }
    stage('Deploy'){
      when{
        branch 'master'
      }
      steps{
        echo 'Deploy'
      }
    }
  }
}