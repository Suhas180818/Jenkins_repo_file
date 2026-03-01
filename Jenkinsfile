pipeline {
    agent any 

    stages {
        stage('TEST') {
            steps {
                echo "This is testing the script"
                sh 'sleep 5'    
            }
        }
        stage('BUILD') {
            steps {
                echo "This is building the script"
                sh '''
                    #!/bin/bash
                    pwd
                    ls -lrt 
                    sleep 
                '''                    
            }
        }
        
    }
}