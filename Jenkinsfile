pipeline {
  agent any
  stages {
    stage('Build Java 8') {
      parallel {
        stage('Build Java 8') {
          agent any
          steps {
            sh '''echo I am a $BUZZ_NAME
./jenkins/build.sh'''
            archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
          }
        }

        stage('Build') {
          steps {
            archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
          }
        }

      }
    }

    stage('Build Java 7') {
      parallel {
        stage('Build Java 7') {
          agent any
          steps {
            sh './jenkins/test-all.sh'
            junit '**/surefire-reports/**/*.xml'
          }
        }

        stage('Build 7') {
          agent any
          environment {
            BUZZ_NAME = 'Java 8 Bee'
          }
          steps {
            echo 'Java 8 Bee'
          }
        }

      }
    }

  }
  environment {
    BUZZ_NAME = 'Worker Bee'
  }
}