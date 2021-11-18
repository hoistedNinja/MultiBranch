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
    stage('Stage 1'){
      steps {
        echo "stage 1"
        sh '''
          pwd
          ls
          mkdir -p testingJenkins
          ls
          echo $AAA_TOP_LEVEL_VAR
          env | sort
        '''
      }
      stage('Stage 2'){
        environment {
          AAA_STAGE_LEVEL_VAR= ' stage level env variable'
        }
      steps {
        echo "stage 2"
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
