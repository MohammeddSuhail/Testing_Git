pipeline {
  agent any

  parameters{
    string defaultValue: '', name: 'region_name', description: 'Enter the region name.'
        string defaultValue: '', name: 'linked_region_name', description: 'Enter the name of the ACQ region to link with.'
        string defaultValue: '', name: 'linked_region_path', description: 'Enter the path of the ACQ region to link with.'
        string defaultValue: '', name: 'package_name', description: 'Enter the file name of the packaged tar file.'

        choice choices: ['Oracle', 'Postgres'], name: 'Database_Type', description: 'Enter the name of the DB to connect to.'

        string defaultValue: '', name: 'icg_schema', description: 'Enter the ICG schema name.'
        string defaultValue: '', name: 'acq_schema', description: 'Enter the linked ACQ schema name.'


        string defaultValue: '', name: 'tpe_port', description: 'Enter an unused TPE server port.'
        string defaultValue: '', name: 'tns_port', description: 'Enter an unused J3270 port.'
        string defaultValue: '', name: 'tls_port', description: 'Enter an unused TPE server TLS port.'
  }
  
  stages {
    stage('Build') {
      steps {
        echo params.region_name
      }
    }
  }
}
