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
        # Build images locally and start mine
        sh 'docker-compose -f local.docker-compose.yml up --build --force-recreate'

        echo "start building image"
        dir ('tomcat') {
            sh 'docker build .'
        }
      }   
    }
  }
}
