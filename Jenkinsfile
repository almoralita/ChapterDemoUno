pipeline {
  agent any
  stages {
    stage('Buzz Buzz') {
      parallel {
        stage('Buzz Buzz') {
          agent any
          steps {
            echo 'Buzz Bees'
            echo 'Buzz'
          }
        }

        stage('Java 7') {
          steps {
            stash(name: 'Buzz 7', includes: 'target/**')
          }
        }

        stage('Java 8') {
          steps {
            stash(name: 'Buzz Java 8', includes: 'target/**')
          }
        }

      }
    }

    stage('Bees') {
      parallel {
        stage('Bees') {
          agent any
          steps {
            echo 'Bees Buzzing!'
          }
        }

        stage('Test A7') {
          steps {
            sh 'echo "Hola"'
            unstash 'Buzz Java 7'
          }
        }

        stage('Test B7') {
          steps {
            sh 'echo "Hola"'
            unstash 'Buzz Java 8'
          }
        }

        stage('Test A8') {
          steps {
            sh 'echo "Hola"'
            unstash 'Buzz Java 7'
          }
        }

        stage('Test B 8') {
          steps {
            sh 'echo "Hola"'
            unstash 'Buzz Java 8'
          }
        }

      }
    }

  }
}