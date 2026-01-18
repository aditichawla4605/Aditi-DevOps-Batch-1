pipeline {
    agent any

    stages {

        stage('Build') {
            agent none
            stages {

                stage('Build Stage') {
                    agent any
                    steps {
                        echo 'Compiling application...'
                        bat '''
                        if not exist build mkdir build
                        echo Build output file > build\\output.txt
                        '''
                    }
                }

                stage('Archive Artifacts') {
                    agent any
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
