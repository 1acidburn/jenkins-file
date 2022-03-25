#!/usr/bin/env groovy
node {
   load "Projects.groovy"
   echo "${env.DB_URL}"
   echo "${env.DB_URL2}"
}

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
      stage('UpdateDB') {
         when {
            expression {
               UPDATE_DB == 'true'
            }
         }
         steps {
            echo 'Update_DB expression works!'
         }
      
            }
      
            
      // Expression based when example with AND
      stage('ImportRDDP') {
         when {
            expression {
               IMPORT_RDDP == 'true'
            }
         }
         steps {
            echo 'IMPORT_RDDP expression works!'
         }
      
            }
   }
}
