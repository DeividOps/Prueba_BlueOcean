pipeline {
    agent any
    stages {
        if (Branches == 'main') {
                echo 'Desa'
        }
        else{
        stage('Build') {
            steps {
                echo 'Build completed testing2'
            }
        }
        stage('Test') {
            steps {
                echo 'Test completed testing2'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy completed testing2'
            }
        }
    }
    }

}