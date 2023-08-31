pipeline {
  agent any

  parameters{
    choice choices: ['JENKIVP','JENKREL'], name: 'Region'
  }
  
  stages {
    stage('Build') {
      steps {
        script{
          if (params.Region == 'JENKIVP') {
            echo "ivp: ${params.Region}"
          }else{
            echo "rel: ${params.Region}"
          }
        }
      }
    }
  }
}
