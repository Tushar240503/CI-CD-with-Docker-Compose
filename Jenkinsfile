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
                    def cmd="docker-compose -f docker-compose.yaml up --detach "
                    sshagent(['aws']) {
                        sh "scp docker-compose.yaml ec2-user@ip:/home/ec2-user"
                        sh "ssh -o StrictHostKeyChecking=no ec2-user@54.224.249.251 ${cmd}"
                    }
                }
            }
        }
    }
}
