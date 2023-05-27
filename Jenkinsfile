pipeline {
    agent any
    stages {
        stage("test") {
            steps {
                script {
                   echo "Testing the application..."
                }
            }
        }
        stage("build") {
            steps {
                script {
                    echo "building the application....."
                }
            }
        }
        stage("deploy") {
            steps {
                script {
                    def dockerCmd = 'docker run -p 80:80 -d fatima0/my-repo:my-app-3.0'
                    sshagent(['ec2-server-key']) {
                        sh "ssh -o StrictHostKeyChecking=no ec2-user@13.232.132.218 ${dockerCmd}"
                    }
                }
            }
        }
    }   
}
