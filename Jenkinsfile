pipeline {
    agent any
    
    stages {
        stage('Print Messages') {
            steps {
                script {
                    // Get the current branch name
                    def branchName = env.BRANCH_NAME
                    echo "Current branch: ${branchName}"
                    
                    // Access program.dat file
                    def filePath = "/var/lib/jenkins/jobs/multibranch/branches/${branchName}/builds/lastSuccessfulBuild/program.dat"
                    
                    // Check if the file exists
                    if (fileExists(filePath)) {
                        // Read and print the contents of the file
                        def fileContents = readFile(filePath)
                        echo "Contents of program.dat: ${fileContents}"
                    } else {
                        echo "program.dat file not found for branch: ${branchName}"
                    }
                    
                    // Echo different messages based on the branch name
                    switch (branchName) {
                        case 'first':
                            echo 'one'
                            break
                        case 'second':
                            echo 'two'
                            break
                        case 'third':
                            echo 'three'
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

def fileExists(filePath) {
    try {
        return sh(script: "[ -e ${filePath} ]", returnStatus: true) == 0
    } catch (Exception e) {
        return false
    }
}

def readFile(filePath) {
    try {
        return readFile(filePath).trim()
    } catch (Exception e) {
        return null
    }
}
