pipeline {
    agent any
    
    stages {
        stage('Print Messages') {
            steps {
                script {
                    // Get the current branch name
                    def branchName = env.BRANCH_NAME
                    echo "Current branch: ${branchName}"
                    
                    // Echo different messages based on the branch name
                    if (branchName == 'first') {
                        echo 'one'
                    } else if (branchName == 'second') {
                        echo 'two'
                    } else if (branchName == 'third') {
                        echo 'three'
                    } else {
                        echo 'Branch name not recognized'
                    }
                }
            }
        }
    }
}
