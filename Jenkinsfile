pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    build job: 'PES2UG21CS197-1', wait: false
                    sh 'g++ main.cpp -o output'
                }
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deployed!'
            }
        }
    }

    post {
        failure {
            error 'Pipeline Failed'
        }
    }
}
