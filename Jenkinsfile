pipeline {
  agent {
    docker {
      image 'ubuntu'
      args 'latest'
    }
    
  }
  stages {
    stage('Push to Dev') {
      steps {
        echo 'PUSH to DEV'
      }
    }
    stage('TEST') {
      steps {
        parallel(
          "TEST": {
            echo 'Automation Test'
            
          },
          "Pentest": {
            echo 'Pentest OK'
            
          }
        )
      }
    }
    stage('Push to UAT') {
      steps {
        echo 'Push to UAT'
      }
    }
    stage('Test') {
      steps {
        parallel(
          "Test": {
            echo 'Automation Test'
            
          },
          "Manual UI Test": {
            echo 'Manual UI Test'
            
          },
          "Stress Test": {
            echo 'Strest Test'
            
          }
        )
      }
    }
    stage('Push to Poduction') {
      steps {
        echo 'Pushed to Production'
      }
    }
  }
}