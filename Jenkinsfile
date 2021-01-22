pipeline {
  
  agent any

  // environment {
  //   DO_ERROR = "1"
  // }

  parameters {
    booleanParam(name: "runDerrpage", defaultValue: false, description: "Boolean to determine whether or not to elicit error")
  }

  stages {
    
    stage("error") {

      when {
        expression {
          params.runDerrpage == true
        }
      }

      steps {
        echo "Uh, oh! Now you've done it!"
        error "The test has failed. TRY AGAIN!"
      }

    }
    
    stage("build") {

      when {
        expression {
          params.runDerrpage == false
        }
      }

      steps {
        echo "Building the application..."
      }
    }

    stage("test") {
      
      when {
        expression {
          params.runDerrpage == false
        }
      }

      steps {
        echo "Testing the application..."
      }
    }

    stage("deploy") {
      
      when {
        expression {
          params.runDerrpage == false
        }
      }

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