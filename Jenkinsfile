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

        stage('Test') {
          steps {
            echo "${VERSION}"
          }
        }

      }
    }

  }
  environment {
    VERSION = readMavenPom().getVersion()
  }
}