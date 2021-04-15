pipeline {
  agent any

  stages {
    stage('Clean') {
      steps {
        sh './gradlew clean'
      }
    }
    stage('Compile') {
      steps {
        sh './gradlew compileJava'
      }
    }
    stage('Tests') {
      steps {
        sh './gradlew test'
      }
    }
  }
}