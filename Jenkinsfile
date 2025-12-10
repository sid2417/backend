pipeline {
    agent{
        label 'AGENT-1'
    }
    
   
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }
    stages{
        stage('Install Dependencies'){
            steps{
                sh"""
                    pwd
                    ls -ltr
                    npm install
                    ls -ltr
                    
                    

                """
            }
        }
            
    }

    post { 
        always { 
            echo 'This message will always say Hello again!'
        }
        aborted { 
            echo 'The stage is aborted'
        }
        failure { 
            echo 'The stage is failure'
        }
        success { 
            echo 'The stage is success'
        }
    }
}