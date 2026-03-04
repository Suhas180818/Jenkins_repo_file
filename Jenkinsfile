pipeline {
    agent any 
    
    parameters{
        string(name:'NAME' , defaultValue:'' ,  description:'')
        booleanParam(name:'SKIP_TEST', defaultValue:'false', description:'Checking to skip the test')
        choice(name:'BRANCH', choices:['main','feature','suhas'], description:'where the branch to deploy')

    }  
  
    stages {

        stage ('CHECKOUT') {
            steps {
                checkout ([ $class : 'GitSCM'
                            branches: [[name: '*/suhas']], 
                            extensions: [], 
                            userRemoteConfigs: [[
                                credentialsId: 'Git_repo_acess', 
                                url: 'https://github.com/Suhas180818/Jenkins_repo_file.git'
                            ]]
                ])    
            }
        }
        
        stage ('TRY_CATCH') {
           steps{
                catchError (buildResult:'FAILURE', stageResult:'FAILURE') {
                    echo "SKIP_TEST: ${params.SKIP_TEST}"
                    exit 1            
                }
            } 
        } 
        
        stage ('TRY_CATCH2') {
            steps{
                script {
                    try {
                        sh '''
                            sleep 5
                            exit 1
                        '''
                    }

                    catch (err) {
                        echo "Error catched : ${err}"
                        currentBuild.result = "SUCCESS"                    
                    }
                }
            }
        }
        
        stage('TEST') {
            when {
                branch 'main' 
            }
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



