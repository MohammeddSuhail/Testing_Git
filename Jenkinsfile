pipeline {
    agent any
    
    parameters {
        choice (name: 'cus_name',
            choices:  ['ADIQ','Arab_Financial_Services_AFS', 'Bank_of_Abyssinia_BoA', 'Currency_Select', 'Dashen', 'Dock_Conductor_CDT', 
            'Green_Dot', 'ING', 'NBE', 'PayGo_C6', 'PNMS _Argentina_GetNet_SMPS', 'PNMS _Mexico_GetNet_SMPS', 'Retail_Assist', 'Shift4', 
            'TietoEVRY_Sweden', 'Base', 'NETS', 'PNMS', 'Redeban', 'EIT', 'KUVAS', 'LOGBANK', 'CMM_ED', 'NovoPayment', 'Datafast', 'PTBANK', 
            'ICG_ISS', 'ABN_AMRO', 'NonBase', 'PNMS_CHILE', 'Frost_Bank', 'KIWI', 'Synechron'],
            description: 'Enter Your Customer name')

        string(name: 'zipFile_name',
           defaultValue: '/home/cmmicgts/Tar_Automation/CMM_Interchange/Tar_Creation/Zip_File/Interchange_UNIX_AIX.zip', 
           description: 'Enter Zipfile location')

        string(name: 'tar_location',
           defaultValue: '/tmp', 
           description: 'Enter the path where zip should be created')

        string(name: 'version',
           defaultValue: '3.44.6', 
           description: 'Enter ICG Version')
 
    }

    stages {
        stage("Checkout and calling anisble script"){

            steps{
                echo params.customer_name
                echo params.zipFile_name
                echo params.tar_location
                echo params.version
            }
        }
        
    }
}
