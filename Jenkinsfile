pipeline {
    agent any 

    // triggers {
    
    //     upstream (
    //         upstreamProjects: 'AWS access',
    //         threshold: hudson.model.Result.SUCCESS, 
    //     )
    // }


    stages {
        stage ('TEST') {
            
            steps { 
                sh'''
                    echo "This is build stage"
                    sleep 5
                '''
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
                echo "DEVELOPER : ${params.DEVELOPER}"
                sleep 5
            }

        }
    
    } 
}
    




 
