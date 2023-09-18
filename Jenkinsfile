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
                    def dockerCmd='docker run -p 3080:3080 tushar24sharma/docker:1.1.2-20'
                    sshagent(['aws']) {
                        sh "ssh -o StrictHostKeyChecking=no ec2-user@54.224.249.251 ${dockerCmd}"
                    }
                }
            }
        }
    }
}
