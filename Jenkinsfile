pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ -o test_program test.cpp'  // Corrected syntax
                echo 'Build Stage Successful'
            }
        }

        stage('Test') {
            steps {
                sh './test_program'  // Run the compiled program
                echo 'Test Stage Successful'
            }
        }

        stage('Deploy') {
    steps {
        echo 'Deploying the application...'
        sh 'sudo cp test_program /usr/local/bin/'
        echo 'Deployment Successful'
    }
}


    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
