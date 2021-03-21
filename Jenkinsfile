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
                            var = env.dev.tokenize(",").each { server ->
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
                    //var.each { server ->
                    //echo "server are $server"} 
                    //var2 = ['a', 'b', 'c']
                    for (int i = 0; i < var.size(); i++) {
        sh "echo Hello ${var[i]}"
    }
                    }
                }
            }
        }
    
    
    environment { 
        test = "d250lxcmite02,d250lxcmite01"
        dev = "d250lxcde61,d250lxcde62"
    
    }

}