#!/usr/bin/env groovy
pipeline {
   agent any
    
   environment {
      IMPORT_RDDP = 'true'
      UPDATE_DB = 'true'
      EXECUTE_WTC = 'true'
   }
    
   stages {
   
      // skip a stage while creating the pipeline
      stage("A stage to be skipped") {
         when {
            expression { false }  //skip this stage
         }
         steps {
            echo 'This step will never be run'
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
