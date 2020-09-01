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
                sh label: 'output', returnStdout: true, script: 'docker-compose build'
            }
        }
    }
}