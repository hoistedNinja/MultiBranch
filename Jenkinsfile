pipeline {
  agent any
   
  environment {
      // global level env variable
      AAA_TOP_LEVEL_VAR = 'GLOBAL LEVEL Env Variable'
    }
  
  options {
    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
    disableConcurrentBuilds()
  }
  stages{
    stage('STAGE -- 1'){
      steps {
        echo "STAGE -- 1"
        sh '''
          pwd
          ls
          mkdir -p testingJenkins
          ls
          echo $AAA_TOP_LEVEL_VAR
          env | sort
        '''
      }
    }
    stage('STAGE -- 2'){
        environment {
          AAA_STAGE_LEVEL_VAR= ' stage level env variable'
        }
        steps {
          echo "STAGE -- 2"
          sh '''
          pwd
          ls
          mkdir -p testingJenkins
          ls
          echo $AAA_TOP_LEVEL_VAR
          echo $AAA_STAGE_LEVEL_VAR
          env | sort
        '''
      }
    }
    stage('STAGE -- 3'){
        steps {
          echo "STAGE -- 3"
          sh '''
          pwd
          ls
          mkdir -p testingJenkins
          ls
          echo $AAA_TOP_LEVEL_VAR
          echo $AAA_STAGE_LEVEL_VAR
          env | sort
        '''
      }
    }
  }
}
