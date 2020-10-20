pipeline {
  agent none
  options {
    buildDiscarder(logRotator(numToKeepStr: '10'))
    //skipDefaultCheckout true
    //preserveStashes(buildCount: 10)
  }
  stages('VueJS Test and Build')
  {
    stage('VueJS Tests') {
      agent {
        node {
          label 'nodejs'
       }
      }
      steps {
            //checkout scm
              sh '''
                 yarn install
                 yarn test:unit
                 '''
      }
    }
  }
}
