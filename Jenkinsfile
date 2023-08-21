pipeline {
    agent any
    
    parameters {
        string(name: 'CUST_NAME',
           description: 'Enter Your Customer name')

        string(name: 'ZIPFILE_LOC',
           description: 'Enter Zipfile location')

        string(name: 'ZIP_FILE_CREATION_PATH',
           description: 'Enter the path where zip should be created')
 
    }

    stages {
        stage("Checkout and calling anisble script"){

            steps{
                echo params.CUST_NAME
                echo params.ZIPFILE_LOC
                echo params.ZIP_FILE_CREATION_PATH
            }
        }
        
    }
}
