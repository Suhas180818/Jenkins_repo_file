pipeline {
    
    agent { label 'ubuntulinux01' }
    
    stages {
        stage {
           steps{
                echo "This is the bulid"
                sh '''
                    echo "This the shell executed Command in Stage 1"              
                '''
           }  
        }
        stage {  
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



