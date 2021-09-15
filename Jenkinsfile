#!groovy
properties([disableConcurrentBuilds()])

pipeline {
  agent {
    label 'master'
  }
  
  stages {
    stage("create docker image") {
      steps {
        echo "start building image"
        dir ('postgres') {
            sh 'docker build .'
        }
      }   
    }
  }
}
