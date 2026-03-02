pipeline {

    agent any

    stages{
        stage('Build') {
            steps {
                echo "This is the bulid"
                sh '''
                    echo "This the shell executed Command in Stage 1"              
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''
                    #!/bin/bash
                    ls -lrt
                    echo "Shell Command Executing in Stage2"
                    sleep 10 
                ''' 

            }
        }
        stage('Deploy') {
            steps {
                sh '''
                    #!/bin/bash
                    ls -lrt
                    echo "Shell Command Deploying the config file"
                    sleep 5
                ''' 

            }
        }
    }   
}