pipeline {
    agent {
        node {
            label 'zaxserver'
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
        stage('Build app') {
            when {
                branch 'master' // only run these steps on the master branch
            }

            steps {
                statusCode = 
                sh """
                   docker-compose build
                   echo "Exit code: $?"
                """
            }
        }
    }
}