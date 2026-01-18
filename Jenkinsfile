pipeline {
    agent any

    stages {

        stage('Initialize') {
            steps {
                bat '''
                echo Building branch: %BRANCH_NAME%
                echo Build Number: %BUILD_NUMBER%
                '''
            }
        }

        stage('Build') {
            steps {
                bat 'echo "Compiling"'
                bat 'echo "Build Version 1.0" > build-info.txt'
                archiveArtifacts artifacts: 'build-info.txt', allowEmptyArchive: true
            }
        }

        stage('Test') {
            steps {
                bat 'echo "Tests Passed"'
            }
        }

        stage('Deploy') {
            steps {
                bat 'echo "Deploying application"'
            }
        }

        stage('End') {
            steps {
                bat 'echo "Pipeline completed successfully"'
            }
        }
    }
}
