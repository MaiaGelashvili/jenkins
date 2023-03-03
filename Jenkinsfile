def TAG_SELECTOR = "UNINTIALIZED"
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
                   stage('Build') {
            steps {
                sh "mvn --batch-mode -U deploy"
                script {
                    TAG_SELECTOR = readMavenPom().getVersion()
                }
                echo("TAG_SELECTOR=${TAG_SELECTOR}")
            }
        }
      }
    }

  }
}
