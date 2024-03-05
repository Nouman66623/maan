pipeline {
    agent any
    
    stages {
        stage('Print Messages') {
            steps {
                script {
                    echo 'Hello, this is third-branch'
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
