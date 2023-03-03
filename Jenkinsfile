pipeline {
  agent any
  stages {
    stage('Functional Test') {
      steps {
        bat 'mvn clean test'
      }
    }

    stage('maven version') {
      steps {
        readMavenPom(file: 'pom.xml')
        sh '''pipeline {

    agent any


    environment {
    //Use Pipeline Utility Steps plugin to read information from pom.xml into env variables
    IMAGE = readMavenPom().getArtifactId()
    VERSION = readMavenPom().getVersion()
    }


    stages {

        stage(\'Test\') {
            steps {
                echo "${VERSION}"
            }

        }

    }

}'''
        }
      }

    }
  }