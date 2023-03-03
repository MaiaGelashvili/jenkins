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

        stage('info') {
          steps {
            script {
              def version = sh script: 'mvn help:evaluate -Dexpression=project.version -q -DforceStdout', returnStdout: true
              def artifactId = sh script: 'mvn help:evaluate -Dexpression=project.artifactId -q -DforceStdout', returnStdout: true
            }

          }
        }

      }
    }

  }
}