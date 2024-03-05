pipeline {
    agent any
    
    stages {
        stage('Print Messages') {
            steps {
                script {
                    def branchName = env.BRANCH_NAME
                    echo "Current branch: ${branchName}"
                    
                    switch (branchName) {
                        case 'main':
                            echo 'Hello, this is main branch'
                            break
                        case 'second-branch':
                            echo 'Hello, this is second-branch'
                            break
                        case 'third-branch':
                            echo 'Hello, this is third-branch'
                            break
                        default:
                            echo 'Branch name not recognized'
                    }
                }
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
