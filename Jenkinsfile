pipeline {
  agent any
	environment {
		NAME = 'hello'
	}
  stages {

    stage ('PRINT') {
      steps {
        echo "$NAME" 
        sh '''
		echo $NAME
		echo "Hello"
	        exit 0 
	   '''
      }  
    } 
stage ('TEST PARALLEL') {
    parallel {
    stage ('TEST1') {
      steps {
        echo "This is Test1" 
        sh '''
          echo "p1"
          exit 0
          '''
        }
      } 
      stage ('TEST2') {
      steps {
        echo "This is Test2 stage" 
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
