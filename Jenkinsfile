pipeline {
  agent any

  parameters {
        extendedChoice(name: 'Region_Action', description: 'Select an action for regions. Note: Choose "Delete a Region" option only if Region already exists.', type: 'PT_CHECKBOX', value: 'Delete a Region, Create a Region')
        booleanParam defaultValue: false, name: 'Smoke_Test', description: 'Do you want to perform Smoke Test?'
        string name: 'region_name', description: 'Enter the region name.'
        string name: 'linked_region_name', description: 'Enter the name of the ACQ region to link with.'
        string name: 'linked_region_path', description: 'Enter the path of the ACQ region to link with.'
        string name: 'package_name', description: 'Enter the file name of the packaged tar file.'
        string name: 'Tools_Build_ID', description: 'Enter a tools build id.'
        choice choices: ['oracle', 'postgres'], name: 'Database_Type', description: 'Enter the name of the DB to connect to.'
        string name: 'icg_schema', description: 'Enter the ICG schema name. (If the Database_Type is Postgres)'
        string name: 'acq_schema', description: 'Enter the linked ACQ schema name. (If the Database_Type is Postgres)'
        extendedChoice(name: 'Port_Selection', description: 'Select the port configuration method.', type: 'PT_RADIO', value: 'Auto-Detect Ports, Manual Port Entry')
        string name: 'tpe_port', description: 'Enter an unused TPE server port.'
        string name: 'tns_port', description: 'Enter an unused J3270 port.'
        string name: 'tls_port', description: 'Enter an unused TPE server TLS port.'
    }
    
    stages {

      stage("Verifying parameter values"){
            steps{
                script {
                    echo "reggggggggggggggggggggggggggggg: "
                    echo "$params.Region_Action"
                    
                    echo "$params.Smoke_Test"
                    if(params.Smoke_Test == true){
                        echo "smoke test trueeeeeeeeeeeee"
                    }else{
                        echo "smoke test falseeeeeeeeeeeeeee"
                    }
                    
                    env.valid = "true";

		            if(params.Region_Action.isEmpty() ||params.region_name.isEmpty() || params.linked_region_name.isEmpty() || params.linked_region_path.isEmpty() || params.package_name.isEmpty() || params.Port_Selection.isEmpty() || params.Tools_Build_ID.isEmpty()){
                        env.valid = "false";
                    }

                    if(params.Database_Type == 'postgres' && (params.icg_schema.isEmpty() || params.acq_schema.isEmpty())){
                        env.valid = "false";
                    }

                    if(params.Port_Selection == 'Manual Port Entry' && (params.tpe_port.isEmpty() || params.tns_port.isEmpty() || params.tls_port.isEmpty())){
                        env.valid = "false";
                    }

                    if (params.Database_Type.equals("oracle")) {
                        env.config_file = "region_config_ora";
                        env.db_type = "oracle";
                    }else{
                        env.db_type = "postgres"; //echo env.db_type
                        env.config_file = "region_config_pg";
                    }
                }
            }
        }
        
        
        
        stage("[Linux] Delete old IVP region"){
            when {
                expression { return env.valid.equals("true") && (params.Region_Action == "Delete a Region" || params.Region_Action == "Delete a Region,Create a Region")}
            }
            steps{
                script {
                    echo "deletion of region"
                }
            }
        }
        
        
        stage("[Linux] Create new IVP region"){
            when {
                expression { return env.valid.equals("true") && ( params.Region_Action == "Create a Region" || params.Region_Action == "Delete a Region,Create a Region")}
            }
            steps{
                script {
                    
                    echo "$env.valid"
                    
                    if(env.valid.equals("true")){
                        echo "everything is fine"
                    }else{
                        echo "not fine at all"
                    }
                    
                    echo "$db_type";
                    echo "$config_file";
                    echo "creation of region";
                    
                }
            }
        }




    }
}
