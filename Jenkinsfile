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
      
       // Expression based when example
      stage('ImportRDDP') {
         when {
            expression {
               IMPORT_RDDP == 'true'
            }
         }
         steps {
               load "Projects.groovy" // load varables for RDDP
               echo 'STARTING IMPORT DRRP OPERATION'
               echo "${env.DB_URL}"
               echo "${env.UPDATE_DB}"
               echo "${env.DB_URL2}"
         }
      
            }
      
            
      // Expression based when example with AND
      stage('UPDATEDB') {
         when {
            expression {
               UPDATE_DB == 'true'
            }
         }
         steps {
            echo 'STARTING UPDATEDB OPERATION'
         }
      
            }
   }
}
