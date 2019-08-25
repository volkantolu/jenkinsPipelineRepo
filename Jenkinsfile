pipeline {
  agent any
  stages {
    stage('wait') {
      steps {
        sleep 5
      }
    }
    stage('message') {
      steps {
        echo 'hello world'
      }
    }
    stage('windowsBatchScript') {
      steps {
        script{
          sonuc = bat(script: 'python -m unittest UnitTest.py', returnStdout: true, returnStatus: true)
          //sonuc = bat(script: 'python -m unittest UnitTest.py', returnStdout: true)
          echo sonuc.toString()
          if (sonuc == 1){
            currentBuild.result = 'FAILRUE'
          }
        }
      }
    }
  }
  post {
    always {
      echo 'always show this message'

    }

    success {
      echo 'Show this message when success'

    }

    failure {
      echo 'Show this message when failed'

    }

  }
}
