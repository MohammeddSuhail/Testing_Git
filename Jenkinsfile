pipeline {
  agent any

  parameters {
        extendedChoice(name: 'Region_Action', description: 'Select an action for regions. Note: Choose "Delete a Region" option only if Region already exists.', type: 'PT_RADIO', value: 'Create a Region, Delete a Region')
        string name: 'region_name', description: 'Enter the region name.'
        string name: 'linked_region_name', description: 'Enter the name of the ACQ region to link with.'
        string name: 'linked_region_path', description: 'Enter the path of the ACQ region to link with.'
        string name: 'package_name', description: 'Enter the file name of the packaged tar file.'
        choice choices: ['Oracle', 'Postgres'], name: 'Database_Type', description: 'Enter the name of the DB to connect to.'
        string name: 'icg_schema', description: 'Enter the ICG schema name. (If the Database_Type is Postgres)'
        string name: 'acq_schema', description: 'Enter the linked ACQ schema name. (If the Database_Type is Postgres)'
        extendedChoice(name: 'Port_Selection', description: 'Select the port configuration method.', type: 'PT_RADIO', value: 'Auto-Detect Ports, Manual Port Entry')
        string name: 'tpe_port', description: 'Enter an unused TPE server port.'
        string name: 'tns_port', description: 'Enter an unused J3270 port.'
        string name: 'tls_port', description: 'Enter an unused TPE server TLS port.'
        string name: 'Tools_Build_ID', description: 'Enter a tools build id.'
    }
    
    stages {

      stage("Verifying parameter values"){
            steps{
                script {
                    if (params.Database_Type.equals("Oracle")) {
                        env.config_file = "region_config_ora";
                        env.db_type = "Oracle";
                    }else{
                        env.db_type = "Postgres"; //echo env.db_type
                        env.config_file = "region_config_pg";
                    }
                }
            }
        }
        
        stage("[Linux] Create new IVP region"){
            steps{
                script {
                    
                    echo "$db_type";
                    echo "$config_file";
                    echo "creation of region";
                    
                }
            }
        }



        stage("[Linux] Delete old IVP region"){
            steps{
                script {
                    echo "deletion of region"
                }
            }
        }

    }
}
