properties([
  parameters([
    [
      $class: 'ChoiceParameter',
      choiceType: 'PT_SINGLE_SELECT',
      name: 'Environment',
      script: [
        $class: 'ScriptlerScript',
        scriptlerScriptId:'Environments.groovy'
      ]
    ],
    [
      $class: 'CascadeChoiceParameter',
      choiceType: 'PT_SINGLE_SELECT',
      name: 'Host',
      referencedParameters: 'Environment',
      script: [
        $class: 'ScriptlerScript',
        scriptlerScriptId:'HostsInEnv.groovy',
        parameters: [
          [name:'Environment', value: '$Environment']
        ]
      ]
   ]
 ])
])

pipeline {
  agent any
  stages {
    stage('Build') {
      steps {

        steps{
                checkout    changelog: false,
                            poll: false,
                            scm: [$class: 'GitSCM',
                                branches: [[name: 'main']],
                                extensions: [],
                                userRemoteConfigs: [url: 'ssh://git@bitbucket.am.tsacorp.com:7999/aa/cmm_interchange.git']]]

        
        
        echo "${params.Environment}"
        echo "${params.Host}"
      }
    }
  }
}
