#!groovy

node {
  stage('checkout') {
     checkout scm
  }

  stage('check tools') {
     sh "pwd"
     sh "./gradlew --version"
  }

  stage('clean') {
     sh "./gradlew clean"
  }

  stage('test') {
     sh "./gradlew :PuntoVenta:test"
  }

  stage('packaging') {
     sh "./gradlew :PuntoVenta:war"
  }

  stage('deploying') {
     sh "./gradlew :PuntoVenta:deployTest"
  }

}
