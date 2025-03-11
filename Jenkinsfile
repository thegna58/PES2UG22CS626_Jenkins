pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'g++ -o test_program test.cpp'
                echo 'Build Stage Successful'
            }
        }

        stage('Test') {
            steps {
                sh './test_program'
                echo 'Test Stage Successful'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                sh 'mkdir -p $HOME/bin && cp test_program $HOME/bin/'
                echo 'Deployment Successful'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
