pipeline {
  agent any

  parameters{
        string name: 'region_name', description: 'Enter the region name.'
        string name: 'linked_region_name', description: 'Enter the name of the ACQ region to link with.'
        string name: 'linked_region_path', description: 'Enter the path of the ACQ region to link with.'
        string name: 'package_name', description: 'Enter the file name of the packaged tar file.'

        choice choices: ['Oracle', 'Postgres'], name: 'Database_Type', description: 'Enter the name of the DB to connect to.'

        string name: 'icg_schema', description: 'Enter the ICG schema name. (If the Database_Type is Postgres)'
        string name: 'acq_schema', description: 'Enter the linked ACQ schema name. (If the Database_Type is Postgres)'

        extendedChoice(name: 'Port_Selection', description: 'Select the port configuration method.', type: 'PT_RADIO', value: 'Auto-Detect Ports, Manual Port Entry')
    
        string  name: 'tpe_port', description: 'Enter an unused TPE server port.'
        string name: 'tns_port', description: 'Enter an unused J3270 port.'
        string name: 'tls_port', description: 'Enter an unused TPE server TLS port.'

        string name: 'Tools_Build_ID', description: 'Enter a tools build id.'
    
  }
  
  stages {
    stage('Build') {
      steps {
        echo params.Port_Selection
      }
    }
  }
}
