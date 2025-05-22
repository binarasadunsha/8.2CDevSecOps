pipeline {
    agent any

    stages {
        stage('Security Scan') {
            steps {
                echo 'Running security scan'
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
            emailext (
                to: 'binarasadunsha22774@gmail.com',
                subject: "SUCCESS: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                body: "The build was successful!\nCheck the details here: ${env.BUILD_URL}"
            )
        }

        failure {
            emailext (
                to: 'binarasadunsha22774@gmail.com',
                subject: "FAILURE: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                body: "The build has failed.\nCheck the details here: ${env.BUILD_URL}"
            )
        }
    }
}
