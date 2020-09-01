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
                not {
                    branch 'master'
                }
            }

            steps {
                sh label: 'output', returnStdout: true, script: 'docker-compose build'
            }
        }
    }
}