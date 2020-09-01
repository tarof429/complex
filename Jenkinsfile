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
            steps {
                output = sh(label: 'output', returnStdout: true, script: 'docker-compose build').trim()
            }
            post {
                always {
                    sh 'echo "$output"'
                }
            }
        }
    }
}