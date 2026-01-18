pipeline {
    agent any

    stages {

        stage('Build') {
            stages {

                stage('Build Stage') {
                    steps {
                        echo 'Compiling application...'
                        bat '''
                        if not exist build mkdir build
                        echo Build output file > build\\output.txt
                        '''
                    }
                }

                stage('Archive Artifacts') {
                    steps {
                        echo 'Archiving build artifacts'
                        archiveArtifacts artifacts: 'build/**', fingerprint: true
                    }
                }

            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }

        stage('End') {
            steps {
                echo 'Pipeline completed'
            }
        }
    }
}
