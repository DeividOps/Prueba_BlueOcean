pipeline {
    def call(String buildResult) {
            if ( buildResult == "SUCCESS" ) {
            slackSend color: "good", message: "Job: ${env.JOB_NAME} with buildnumber ${env.BUILD_NUMBER} was successful"
            }
            else if( buildResult == "FAILURE" ) { 
            slackSend color: "danger", message: "Job: ${env.JOB_NAME} with buildnumber ${env.BUILD_NUMBER} was failed"
            }
            else if( buildResult == "UNSTABLE" ) { 
            slackSend color: "warning", message: "Job: ${env.JOB_NAME} with buildnumber ${env.BUILD_NUMBER} was unstable"
            }
            else {
            slackSend color: "danger", message: "Job: ${env.JOB_NAME} with buildnumber ${env.BUILD_NUMBER} its resulat was unclear"	
            }
    }
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
        stage('Test') {
            steps {
                echo 'Test completed testing'
            }
        }
        stage('Deploy') {
            steps {
                script { 
                    for (int i = 0; i < var.size(); i++) {
        sh "echo Hello ${var[i]}"
    }
                    }
                }
            }
        }

        
    
    
    environment { 
        test = "d250lxcmite02,d250lxcmite01"
        dev = "d250lxcde61,d250lxcde62,d250lxcde63"
    
    }

}