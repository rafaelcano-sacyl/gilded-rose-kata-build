pipeline {
    agent any

    stages {
        stage('GitHub') {
            steps {
                git branch: 'javadoc', url: 'http://github.com/rafaelcano-sacyl/gilded-rose-kata-build'
            }
        }
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
        stage('Check') {
            steps {
                sh './gradlew check'
            }
        }
        stage('JavaDoc') {
            steps {
                sh './gradlew javadoc'
            }
        }
        stage('JaCoCo') {
            steps {
                sh './gradlew jacocoTestReport'
            }
        }
    }

    post {
        always {
            javadoc javadocDir: 'build/docs/javadoc', keepAll: false
            jacoco()
        }
    }
}