pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    switch(env.BRANCH_NAME){
                        case 'testing':
                            echo 'la rama es testing'
                            for (int i=0; i < test; i++)
                            echo '' + test[i]
                            break
                        case 'main':
                            echo 'la rama es main'
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
                echo 'Deploy completed testing'
            }
        }
    }
    
    environment { 
        test = "uno,dos,tres"
    
    }

}