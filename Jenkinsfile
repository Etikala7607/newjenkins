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
        stage('Backup Jenkins Logs') {
            steps {
                sh '''
                    # Set the date and time format
                    DATE=$(date +'%Y-%m-%d-%H-%M-%S')

                    # Jenkins home directory
                    JENKINS_HOME="/var/lib/jenkins"

                    # S3 bucket and path
                    S3_BUCKET="your-s3-bucket"
                    S3_PATH="jenkins-logs/${DATE}.log"

                    # Path to AWS CLI executable
                    AWS_CLI="/usr/local/bin/aws"

                    # Backup Jenkins logs to S3
                    $/usr/local/bin/awss3 cp "${/var/lib/jenkins}/jenkins.log" "s3://${jenkins-logzz}/${jenkins-logs/${DATE}.log}"
                '''
            }
        }
    }
        }
}
