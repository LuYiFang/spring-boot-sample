pipeline {
  agent any
  stages {
    stage('checkout project') {
      steps {
        checkout scm
      }
    }
    stage('test') {
      steps {
        junit 'target/surefire-reports/*.xml'
      }
    }
    stage('package') {
      steps {
        archiveArtifacts 'target/spring-boot-sample-data-rest-0.1.0.jar '
      }
    }
    stage('deploy') {
      steps {
        sh 'make deploy-default'
      }
    }
  }
}