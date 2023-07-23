pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      agent any
      steps {
        sh './jenkins/build.sh'
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