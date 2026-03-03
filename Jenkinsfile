pipeline {
    
    parameters{
        string(name:'NAME' , defaultValue:'' ,  description:'')
        booleanParam(name:'SKIP_TEST', defalutvalue:'false', description:'Checking to skip the test')
        choice(name:'BRANCH', choices:['main','feature','suhas'], description:'where the branch to deploy')

    }

    agent any 

    
    stages {
        stage ('BUILD') {
           steps{
                echo "NAME: ${params.NAME}"
                echo "SKIP_TEST: ${params.SKIP_TEST}"
                echo "BRANCH: ${params.BRANCH}"
                
            }  
        }
        stage ('TEST') {  
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



