pipeline {
    agent any

    stages {
        stage('Test Email') {
            steps {
                echo 'Running test build...'
            }
        }
    }

    post {
        success {
            emailext(
                to: 'your_email@example.com',
                subject: "SUCCESS: Jenkins Build #${env.BUILD_NUMBER}",
                body: """\
                ✅ Test Build #${env.BUILD_NUMBER} succeeded!
                Job: ${env.JOB_NAME}
                Console log: ${env.BUILD_URL}console
                """
            )
        }

        failure {
            emailext(
                to: 'your_email@example.com',
                subject: "FAILURE: Jenkins Build #${env.BUILD_NUMBER}",
                body: """\
                ❌ Test Build #${env.BUILD_NUMBER} failed!
                Job: ${env.JOB_NAME}
                Console log: ${env.BUILD_URL}console
                """
            )
        }
    }
}
