#!/usr/bin/env groovy

pipeline {
    agent any
    stages {
        stage('test') {
            steps {
                script {
                    echo "Testing the application..."
                }
            }
        }
        stage('build') {
            steps {
                script {
                    echo "Building the application..."
                }
            }
        }
        stage('deploy') {
            steps {

                script {
                    def cmd='docker run -p 3000:3000 -d tushar24sharma/docker:4.1 '
                    sshagent(['ubuntu']) {
                        sh "ssh -o StrictHostKeyChecking=no ubuntu@13.233.85.187 ${cmd}"

    // some block
                    }
                }
            }
        }
    }
}
