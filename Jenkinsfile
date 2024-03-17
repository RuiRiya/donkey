pipeline {
  agent any
  stages {
    stage('test') {
      parallel {
        stage('test') {
          steps {
            echo 'testing'
          }
        }

        stage('test2') {
          steps {
            sleep 10
            echo 'parallel testing'
          }
        }

      }
    }

    stage('build') {
      steps {
        sh '''pwd
ls'''
        echo 'building'
      }
    }

    stage('deploy-to-test-server') {
      steps {
        sleep 5
        writeFile(file: 'abc', text: 'hi all')
      }
    }

  }
}