#!/usr/bin/env groovy
pipeline {
   agent any
    
   environment {
      IMPORT_RDDP = 'true'
      UPDATE_DB = 'true'
      EXECUTE_WTC = 'true'
   }
  
   // using the Timestamper plugin we can add timestamps to the console log
    options {
        timestamps()
    }
   
   stages {
   
      // skip a stage while creating the pipeline
      stage("Import Database operation") {
         when {
            expression { false }  //skip this stage
         }
         steps {
            echo 'Import Database operation will never be run'
         }
      }
      
            
      // Expression based when example with AND
      stage('full deployment') {
         when {
            expression {
               IMPORT_RDDP == 'true' && UPDATE_DB == 'true' && EXECUTE_WTC == 'true'
            }
         }
         steps {
            echo 'IMPORT_RDDP with UPDATE_DB expression works!'
         }
      
      
          
      
           
     
   }
   }
}
