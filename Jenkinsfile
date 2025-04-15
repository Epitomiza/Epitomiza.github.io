pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'make'
            }
        }

        stage('Test') {
            steps {
                 sh 'make check'
                junit 'reports/**/*.xml' 
            }
        }

        stage('Deploy to Staging') {
            steps {
                sh 'make publish' 
            }
        }

        stage('Acceptance Tests') {
            steps {
                sh 'make publish' 
            }
        }

        stage('Deploy to Production') {
            when {
                expression { currentBuild.resultIsBetterOrEqualTo('SUCCESS') }
            }
            steps {
                sh 'make publish' 
            }
        }
    }
}
