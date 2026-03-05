pipeline {
    agent any 

    parameters {
        string(name:'DEVELOPER',defaultValue:'',description:'Enter your name')
        booleanParam(name:'SKIP_TEST',defaultValue:'fasle',description:'')
    }

    environment {
        DOCKER_USER = 'suhas'
        AWS_CREDENTIALS = '123456789'
    } 

    stages {
        stage ('TEST') {
            agent {label 'slave1'}
            steps {
                echo "This is the stage running in Test"
                echo "DOCKER_USER : $(env.DOCKER_USER)"
                echo "AWS_CREDENTIALS : $(env.AWS_CREDENTIALS)"
            }
        }
        stage ('Build') {
            parallel{
                stage ('WINDOWS_TESTING') {
                    steps {
                       echo "Building the project in WINDOWS OS"     
                    }
                }
                stage ('MACOS_TESTING') {
                    steps {
                       echo "Building the project in MAC OS"     
                    }
                }

            }
        }
        stage ('DEPLOY') {
            steps {
                echo "The stage is Deloying"
                echo "DEVELOPER : $(params.DEVELOPER)"
                sleep 5
            }

        }
    
    } 
}
    




 
                // checkout ([
                //     $class : 'GitSCM'
                //     branches: [[name: '*/main']],
                //     extensions: [],
                //     userRemoteConfigs: [[
                //         credentialsId:'Git_repo_acess'
                //         url: 'https://github.com/Suhas180818/Jenkins_repo_file.git'
                //     ]]    
                // ])
