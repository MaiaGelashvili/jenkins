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
            bat 'mvn --version'
          }
        }

      }
    }

    stage('maven') {
      steps {
        bat 'mvn --version'
      }
    }

  }
}
