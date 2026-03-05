pipeline {
    agent any 

    
    parameters{
        string(name:'NAME' , defaultValue:'suhas' ,  description:'')
        booleanParam(name:'SKIP_TEST', defaultValue:'false', description:'Checking to skip the test')
        choice(name:'BRANCH', choices:['main','feature','suhas'], description:'where the branch to deploy')

    }  
  
    stages {         
        // stage ('CHECK_OUT') {      
        //     steps {                
        //         catchError(buildResult:'SUCCESS',stageResult:'SUCCESS')
                
        //         checkout ([
        //             $class : 'GitSCM'
        //             branches: [[name: '*/main']],
        //             extensions: [],
        //             userRemoteConfigs: [[
        //                 credentialsId:'Git_repo_acess'
        //                 url: 'https://github.com/Suhas180818/Jenkins_repo_file.git'
        //             ]]    
        //         ])

        //         sh '''
        //             ls -lrt 

                
        //         '''         
        //     }
        // }
        
        stage('TEST') {
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



