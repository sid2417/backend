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

    environment { 
        appVersion = ''
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
        stage('Read Version'){
			steps{
				script{
					def packageJson = readJSON file: 'package.json'
					appVersion = packageJson.version
					
					echo "current_version: ${env.appVersion}"
				
				}
				
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