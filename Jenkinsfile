pipeline {
    agent {
        node {
            label 'ubuntu-build-server'
        }
    }

    environment {
        APP_NAME = "complex"
    }

    stages {
        stage('Initializing build') {
            steps {
                sh """
                env
                """
            }
        }
    }
}