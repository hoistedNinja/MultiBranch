pipeline {
  agent { 
    label "master"
  }
  options {
    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
    disableConcurrentBuilds()
  }
  stages{
    stage('main'){
      when {
          branch "main"
        }
      steps {
        echo "Buildiing containers .."
        echo " Testing Containers .."
      }
    }
    stage('development'){
      when {
          branch "development"
        }
      steps {
        echo "Testing containers  .."
        echo "Tesing containers .."
        echo " deploy containers .."
        
      }
    }
    stage('OM Branch'){
      when {
          branch "OM-*"
        }
      steps {
        echo "Testing containers  .."
        echo "Tesing containers .."
        echo " we are in OM branch .."
        
        
      }
    }
    stage('OM Branch-pull request'){
      when {
        anyOf {
          changeRequest target: 'master'
          changeRequest target: 'main'
        }
      }
      steps {
        echo "Testing containers  .."
        echo "Tesing containers .."
        echo " new branch tested"
        
        
      }
    }

  }
}
