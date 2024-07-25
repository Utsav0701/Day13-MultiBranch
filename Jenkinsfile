pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Utsav0701/Day13-MultiBranch.git', branch: env.BRANCH_NAME
            }
        }

        stage('Build') {
            steps {
                script {
                    echo "Building feature branch: ${env.BRANCH_NAME}"
                    sh javac Smaple.javac
                    sh java Sample
                }
            }
        }

        stage('deployment') {
            steps {
                script {
                    echo "Running Deployment on feature branch: ${env.BRANCH_NAME}"
                    sh javac Smaple.javac
                    sh java Sample
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Pipeline succeeded.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}