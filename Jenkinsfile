pipeline {
    agent any 
    
    parameters{
        string(name:'NAME' , defaultValue:'' ,  description:'')
        booleanParam(name:'SKIP_TEST', defaultValue:'false', description:'Checking to skip the test')
        choice(name:'BRANCH', choices:['main','feature','suhas'], description:'where the branch to deploy')

    }
  
    stages {
        stage ('BUILD_1a') {
           steps{
                catchError (buildResult:'FAILURE', stageResult:'FAILURE') {
                    echo "SKIP_TEST: ${params.SKIP_TEST}"
                    exit 1              
                }
            } 
        } 
        stage ('BUILD_1b') {
            steps{
                script {
                    try {
                        sleep 5
                        exit 1
                    }
                    catch (err){
                        echo "Error catched : ${err.getMessage()}"
                        currentStage.result = "SUCCESS"
                    }

                }
            }
        }
        stage('TEST'){
            parallel {
                stage ('WINDOWS_TESTING'){
                    steps {
                        echo "Running in Windows Machine"                    
                    }
                }
                stage('MACOS_TESTING'){
                    steps{
                        echo "Running test for MACOS MAchine"   
                    }
                }
            }
        }
        stage ('FINAL') {  
            steps {
                sh '''
                    #!/bin/bash
                    ls -lrt
                    echo "Shell Command Executing in Stage2"
                    sleep 10 
                ''' 
            }

        }

    }

}



