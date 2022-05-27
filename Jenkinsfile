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
            sh '''echo testing on the chrom'''
          }
        }
        
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