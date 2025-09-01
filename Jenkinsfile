pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Jessica-Kakshapati/EmailConfiguration', branch: 'main'
            }
        }

        stage('Test Email') {
            steps {
                echo "Running test build..."
            }
        }
    }

    post {
        success {
            emailext (
                subject: "Build #${BUILD_NUMBER} - ${JOB_NAME} - SUCCESS",
                body: """
                Jenkins pipeline completed successfully.
                Job: ${JOB_NAME}
                Build Number: ${BUILD_NUMBER}
                """,
                to: "jessikakshapati@gmail.com",
                attachLog: true
            )
        }
        failure {
            emailext (
                subject: "Build #${BUILD_NUMBER} - ${JOB_NAME} - FAILED",
                body: """
                Jenkins pipeline has failed.
                Job: ${JOB_NAME}
                Build Number: ${BUILD_NUMBER}
                """,
                to: "jessikakshapati@gmail.com",
                attachLog: true
            )
        }
    }
}
