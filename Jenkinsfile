pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Build') {
      when {
        branch 'fix-123'
      }
      steps {
        echo "hwllow workd "
      }
    }
    stage('testing on chrome'){
      parallel{

        stage('testing on chrome'){
          steps{
            echo 'tested on chrome'
          }
        }
        stage('testing on firefox'){
          steps{
            echo 'testing on chrome'
          }
        }

      }
    }
    stage('Deploy'){
      steps{
        echo 'deployed to the test'
      }
    }
  }
  post {
    always {
        junit(
          allowEmptyResults: true, 
          testResults: '**/build/test-results/test/*.xml'
        )
    }
  }
}