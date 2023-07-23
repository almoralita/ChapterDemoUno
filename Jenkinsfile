pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      agent any
      steps {
        echo 'Buzz Bees'
        archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
      }
    }

    stage('Bees') {
      agent any
      steps {
        echo 'Bees Buzzing!'
      }
    }

  }
}