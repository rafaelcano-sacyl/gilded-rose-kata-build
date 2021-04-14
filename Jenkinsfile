pipeline {
  agent any
  stages {
    stage('compile') {
      steps {
        sh 'gradlew clean compileJava test'
      }
    }

    stage('echo') {
      steps {
        echo 'Hola'
      }
    }

    stage('blue-ocean') {
      steps {
        echo 'Pipeline creada en Blue Ocean'
      }
    }

  }
}