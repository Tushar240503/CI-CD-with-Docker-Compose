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
                    def cmd= "bash ./server-cmd.sh"
                    sshagent(['aws']) {
                        sh "scp docker-compose.sh ec2-user@52.90.178.142:/home/ec2-user"
                        sh "scp server-cmd.sh ec2-user@52.90.178.142:/home/ec2-user"
                        sh "ssh -o StrictHostKeyChecking=no ec2-user@52.90.178.142 ${cmd}"
                    }
                }
            }
        }
    }
}
