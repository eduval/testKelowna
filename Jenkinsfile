pipeline {
    agent any

    environment {
        // Retrieve Firebase token from Jenkins credentials (type: Secret Text)
        FIREBASE_TOKEN = credentials('firebase-token')
    }

    stages {
             

        stage('Build') {
            steps {
                sh 'Nothing to DO!'
            }
        }

        stage('Test') {
            steps {
                echo 'This is testing.'
            }
        }

        stage('Staging') {
            steps {
                echo 'This is Staging.'
            }
        }

        stage('Production') {
            when {
                branch 'main'
            }
            steps {
                // Deploy to production with token
                sh 'firebase use production-env-devnet --token $FIREBASE_TOKEN'
                sh 'firebase deploy --only hosting --token $FIREBASE_TOKEN'
            }
        }
    }
}
