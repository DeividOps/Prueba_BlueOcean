pipeline {
    agent any
    stages {
        node { 
            try {
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
            } catch (e) {
                //fail the deploy
                currentBuild.result = "FAILED"
                trow e
            } finally {
        // Post build steps here
        /* Success or failure, always run post build steps */
        // send email
        // publish test results etc etc
    }
    
    
        
    environment { 
        test = "d250lxcmite02,d250lxcmite01"
        dev = "d250lxcde61,d250lxcde62,d250lxcde63"
    
        }
    
    }

}

}