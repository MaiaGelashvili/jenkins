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

        stage('maven version') {
          steps {
            sh 'mvn -version'
            script {
              pom = readMavenPom(file: 'pom.xml')
              projectArtifactId = pom.getArtifactId()
              projectGroupId = pom.getGroupId()
              projectVersion = pom.getVersion()
              projectName = pom.getName()
            }

            echo "Building ${projectArtifactId}:${projectVersion}"
          }
        }

      }
    }

  }
}