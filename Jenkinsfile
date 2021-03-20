pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    switch(env.BRANCH_NAME){
                        case 'testing':
                            echo 'la rama es testing'
                            env.test.tokenize(",").each { server ->
                            echo "Server is $server"

                            }
                            break
                        case 'main':
                            echo 'la rama es main'
                            env.dev.tokenize(",").each { server ->
                            echo "Server is $server"
                            }
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
                        echo "Server is $server"
                    }
                }
            }
        }
    
    
    environment { 
        test = "d250lxcmite02,d250lxcmite01,"
        dev = "d250lxcde61,d250lxcde62"
    
    }

}