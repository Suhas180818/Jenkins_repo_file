pipeline {
    
    agent {{label 'ubuntulinux01' && 'ubuntulinux02'}}
    
    stages {
        stage ('TEST') {
           steps{
                echo "This is the bulid"
                sh '''
                    echo "This the shell executed Command in Stage 1"              
                '''
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



