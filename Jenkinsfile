pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                echo "Checking out code..."
                checkout scm
            }
        }
        
        stage('Healthcheck Master') {
            steps {
                echo "Healthcheck Jenkins Master"
                echo "Branch: ${env.BRANCH_NAME}"
                echo "Build: ${env.BUILD_NUMBER}"
                sh '''
                    echo "Checking Jenkins master health..."
                    echo "This is a placeholder for healthcheck logic"
                '''
            }
        }
    }
    
    post {
        always {
            echo "Pipeline completed for branch: ${env.BRANCH_NAME}"
        }
    }
}

