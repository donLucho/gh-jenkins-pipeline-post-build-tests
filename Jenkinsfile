pipeline {
  
  agent any

  stages {
    
    stage("build") {
      steps {
        echo "Building the application..."
      }
    }

    stage("test") {
      steps {
        echo "Testing the application..."
      }
    }

    stage("deploy") {
      steps {
        echo "Deploying the application..."
      }
    }
    
  }

  // continally execute some logic ( always, success, failure) after all stages have been executed
  post {
    always {
      echo "All of your stages have completed..."
    }
    success {  
      echo "Plus, all of your stages have succeeded..."
    }
    failure {
      echo "But one or more of your stages have failed..."
    }
  } 

}