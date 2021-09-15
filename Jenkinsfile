#!groovy
properties([disableConcurrentBuild()])

pipeline {
  agent {
    label 'master'
  }
  
  stages {
    stage("create docker image") {
      staps {
        echo "start building image"
        dir ('intermine_builder') {
            sh 'docker build .'
        }
      }   
    }
  }
}
