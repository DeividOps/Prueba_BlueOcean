pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Test completed testing'{env.BRANCH_NAME}
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