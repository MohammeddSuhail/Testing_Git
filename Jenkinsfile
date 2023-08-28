properties([
  parameters(
    choice (name: 'Region',
            choices:  ['JENKIVP','JENKREL'],
            description: 'Select the Region')
  )

pipeline {
  agent any
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
