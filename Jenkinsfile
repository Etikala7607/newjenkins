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
       
        stage('Backup Jenkins Logs to S3') {
            steps {
                script {
                    // Set the date and time format
                    def date = sh(returnStdout: true, script: 'date +%Y-%m-%d-%H-%M-%S').trim()

                    // Jenkins home directory
                    def jenkinsHome = "/var/lib/jenkins"

                    // S3 bucket and path
                    def s3Bucket = "jenkins-logzz"
                    def s3Path = "jenkins-logs/${date}.log"

                    // Path to AWS CLI executable
                    def awsCli = "/usr/local/bin/aws"

                    // Backup Jenkins logs to S3
                    sh "${awsCli} s3 cp ${jenkinsHome}/jenkins.log s3://${jenkins-logzz}/${s3Path}"
                }
            }
        }
    }
        }


