@Library('jenkins-shared-library')_

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

        post {
        always {
	    /* Use slackNotifier.groovy from shared library and provide current build result as parameter */   
            slackNotifier(currentBuild.currentResult)
            cleanWs()
        }
    }
    
    
    environment { 
        test = "d250lxcmite02,d250lxcmite01"
        dev = "d250lxcde61,d250lxcde62,d250lxcde63"
    
    }

}