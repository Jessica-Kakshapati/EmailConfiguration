post {
    success {
        emailext (
            subject: "Build #${BUILD_NUMBER} - ${JOB_NAME} - SUCCESS",
            body: """
            Hello,

            The Jenkins pipeline has completed successfully.
            Job: ${JOB_NAME}
            Build Number: ${BUILD_NUMBER}
            Status: SUCCESS

            Please find the build log attached.

            Regards,
            Jenkins
            """,
            to: "jessikakshapati@gmail.com",
            attachLog: true
        )
    }
    failure {
        emailext (
            subject: "Build #${BUILD_NUMBER} - ${JOB_NAME} - FAILED",
            body: """
            Hello,

            The Jenkins pipeline has failed.
            Job: ${JOB_NAME}
            Build Number: ${BUILD_NUMBER}
            Status: FAILED

            Please review the attached build log.

            Regards,
            Jenkins
            """,
            to: "jessikakshapati@gmail.com",
            attachLog: true
        )
    }
}
