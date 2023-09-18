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
                    def dockerCmd='docker run hello-world'
                    sshagent(['aws']) {
                        sh "ssh -o StrictHostKeyChecking=no ec2-user@54.224.249.251 ${dockerCmd}"
                    }
                }
            }
        }
    }
}
