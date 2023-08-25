properties([
  parameters([
    [
      $class: 'ChoiceParameter',
      choiceType: 'PT_SINGLE_SELECT',
      name: 'Environment',
      script: [$class: 'ScriptlerScript',
               groovyScript:'''
      import groovy.json.JsonSlurper
      return ["Select:selected", "DEV", "TEST", "STAGE", "PROD"]
      ''']
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
        echo "${params.Environment}"
        echo "${params.Host}"
      }
    }
  }
}
