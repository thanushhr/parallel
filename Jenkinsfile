pipeline {
  agent any
	environment {
		NAME = 'hello'
	}
  stages {

    stage ('PRINT') {
      steps {
        echo "This is print stage" 
        sh '''
		echo $NAME
		echo "over"
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
    environment {
	 DO = 'done'
	}
      steps {
        echo "$DO" 
        sh 'sleep 5'
      }  
    }  
  } 

}
