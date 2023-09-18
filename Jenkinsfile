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
                    def cmd1="chmod 777 server-cmd.sh"
                    def cmd= "docker run hello-world"
                    def cm2="chmod 777 docker-compose.yaml"
                    sshagent(['aws']) {
                        sh "scp docker-compose.yaml ec2-user@52.90.178.142:/home/ec2-user"
                        sh "scp server-cmd.sh ec2-user@52.90.178.142:/home/ec2-user"
                        sh "ssh -o StrictHostKeyChecking=no ec2-user@52.90.178.142 ${cmd1}"
                        sh"ssh -o StrictHostKeyChecking=no ec2-user@52.90.178.142 ${cmd2}"
                        sh "ssh -o StrictHostKeyChecking=no ec2-user@52.90.178.142 ${cmd}"
                    }
                }
            }
        }
    }
}
