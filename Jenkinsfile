pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    switch(env.BRANCH_NAME){
                        case 'testing':
                            echo 'la rama es testing'
                            var = env.test.tokenize(",") 
                            break
                        case 'main':
                            echo 'la rama es main'
                            var = env.dev.tokenize(",")
                            break
                    }
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy completed testing'
                
                
            }
        }
        stage('Test') {
            steps {
                echo 'Test completed testing'
                
                
            }
        }
        
        /*stage('Deploy') {
            steps {
                script { 
                    if ( stage.Test == Success ) {
                        slackSend color: "good", message: "Job: ${env.JOB_NAME} with buildnumber ${env.BUILD_NUMBER} was successful"
                    }
                    else { 
                    slackSend color: "danger", message: "Job: ${env.JOB_NAME} with buildnumber ${env.BUILD_NUMBER} was failed"
                    }               
                }
            
            }
        }*/
    }
    post {
        failure {
            slackSend color: "danger", message: "El despliegue en el ambiente de ${env.JOB_NAME} Con numero de Build: ${env.BUILD_NUMBER} Ha fallado"
        }
        success {
            slackSend color: "good", message: "El despliegue en el ambiente de ${env.JOB_NAME} Con numero de Build: ${env.BUILD_NUMBER} Se realizo correctamente"
        }
    } 
    
    
    environment { 
        test = "d250lxcmite02,d250lxcmite01"
        dev = "d250lxcde61,d250lxcde62,d250lxcde63"
        
    
    }   
    

}
