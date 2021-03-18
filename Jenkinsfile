pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    switch(env.BRANCH_NAME){
                        case 'main':
                            echo 'la rama es main'
                        case 'testing'
                            echo 'la rama es main'
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
    

}