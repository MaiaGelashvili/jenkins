pipeline {
  agent any
  stages {
    stage('parallel stages') {
      parallel {
        stage('Functional Test') {
          steps {
            bat 'mvn clean test'
          }
        }

        stage('build') {
          steps {
            sh 'mvn --version'
          }
        }

      }
    }

  }
}