pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying.....'
            }
        }
        stages {
        // ... define your build stages
        
        // Post-build step to push logs to S3
        post {
            always {
                script {
                    // Set up AWS CLI credentials
                    withAWS(region: 'us-east-1', credentials: '766480565836') {
                        // Upload Jenkins log files to S3
                        sh "aws s3 cp $JENKINS_HOME/jobs/<run>/builds/$BUILD_NUMBER/log s3://jenkins-logzz/"
                    }
                }
            }
        }
        }
        }
}
