pipeline {
  agent "master"
   
  environment {
      // global level env variable
      AAA_TOP_LEVEL_VAR = 'GLOBAL LEVEL Env Variable'
    }
  
  options {
    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
    disableConcurrentBuilds()
  }
  stages{
    stage('Hello'){
      steps {
        echo "hello"
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
  }
}
