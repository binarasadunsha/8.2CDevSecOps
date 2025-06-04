pipeline {
    agent any

    stages {
        stage('Security Scan') {
            steps {
                echo 'Running security scan...'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to AWS EC2 staging server'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running staging tests using Postman'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production server on AWS EC2'
            }
        }
    }

   post {
    success {
        emailext(
            subject: "Jenkins Build SUCCESS: ${JOB_NAME} #${BUILD_NUMBER}",
            body: """Good news!

Job '${JOB_NAME}' [#${BUILD_NUMBER}] was successful.

🔗 Check it here: ${BUILD_URL}
""",
            to: 'binarasadunsha22774@gmail.com',
            attachLog: true
        )
    }

    failure {
        emailext(
            subject: "Jenkins Build FAILURE: ${JOB_NAME} #${BUILD_NUMBER}",
            body: """Oops! Build failed.

Job '${JOB_NAME}' [#${BUILD_NUMBER}]

🔗 View the details: ${BUILD_URL}
""",
            to: 'binarasadunsha22774@gmail.com',
            attachLog: true
        )
    }
}

}
