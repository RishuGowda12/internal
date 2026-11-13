pipeline {
  agent any
  stages {
     stage('Checkout:') {
          steps{
            checkout scm
         }
      }
stage('Build') {
     steps{
        echo 'Checking Python application'
        bat 'python -m py_comppile python.py'
    }
}
stage('Test'){
      steps{
        echo 'excuting automated tests'
        bat 'python -m unittest python'
    }
}
stage('Run Application'){
      steps{
        bat 'python python.py'
    }
  }
}
post{
  success{
        echo 'CI Pipeline completed successfully'
      }
 failure{
       echo 'CI Pipeline failed'
}
}
}
