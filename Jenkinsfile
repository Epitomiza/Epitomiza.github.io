pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Build your web application
            }
        }

        stage('Test') {
            steps {
                // Run tests on your application
            }
        }

        stage('Deploy to Staging') {
            steps {
                // Deploy to a staging environment
            }
        }

        stage('Acceptance Tests') {
            steps {
                // Run acceptance tests
            }
        }

        stage('Deploy to Production') {
            when {
                expression { currentBuild.resultIsBetterOrEqualTo('SUCCESS') }
            }
            steps {
                // Deploy to production if all tests pass
            }
        }
    }
}
