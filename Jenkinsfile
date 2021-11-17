pipeline {
  agent { 
    docker { image 'node:14-alpine'}
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
          node --version
        '''
      }
    }
  }
}
