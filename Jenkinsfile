pipeline {
  agent any

  parameters{
    choice (name: 'Region',
            choices:  ['JENKIVP','JENKREL'],
            description: 'Select the Region')
  }
  
  stages {
    stage('Build') {
      steps {
        if (params.Region == 'JENKIVP') {
          echo "ivp: ${params.Region}"
        }else{
          echo "rel: ${params.Region}"
        }
      }
    }
  }
}
