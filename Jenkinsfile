pipeline {
  agent any
  { docker { image 'maven:3.9.0-eclipse-temurin-11' } }
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
}
