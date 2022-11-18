pipeline {
  agent any	
  stages {

    stage ('PRINT') {
      steps {
        echo "This is Print stage" 
        sh '''
		echo "Hello"
	        exit 0 
	   '''
      }  
    } 
stage ('TEST PARALLEL') {
	environment {
		$NAME = 'Hellllooo'
	}
    parallel {
    stage ('TEST1') {
      steps {
        echo "This is Test stage" 
        sh '''
          echo "p1"
	  $NAME
          exit 0
          '''
        }
      } 
      stage ('TEST2') {
      steps {
        echo "This is Deploy stage" 
        sh '''
          echo "p2"
          exit 0
          '''
          }
        }
      }
    }  
    
    stage ('DEPLOY') {
      steps {
        echo "This is Deploy stage" 
        sh 'sleep 5'
      }  
    }  
  } 

}
