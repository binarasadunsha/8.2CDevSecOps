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
            emailext subject: 'Jenkins Build SUCCESS: ${JOB_NAME} #${BUILD_NUMBER}',
                     body: "Good news!\n\nJob '${JOB_NAME} [${BUILD_NUMBER}]' was successful.\n\nCheck it here: ${BUILD_URL}",
                     to: 'binarasadunsha22774@gmail.com'
        }
        failure {
            emailext subject: 'Jenkins Build FAILURE: ${JOB_NAME} #${BUILD_NUMBER}',
                     body: "Oops!\n\nJob '${JOB_NAME} [${BUILD_NUMBER}]' failed.\n\nCheck it here: ${BUILD_URL}",
                     to: 'binarasadunsha22774@gmail.com'
        }
    }
}
