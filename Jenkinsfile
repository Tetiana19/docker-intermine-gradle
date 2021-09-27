#!groovy
properties([disableConcurrentBuilds()])

pipeline {
  agent {
    label 'master'
  }
  
  stages {
    stage("create docker image") {
      steps {
        sh './mkdatadirs.sh local.docker-compose.yml'
        echo "start building image"
        dir ('tomcat') {
            sh 'docker build .'
        }
      }   
    }
  }
}
