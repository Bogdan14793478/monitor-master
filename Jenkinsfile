pipeline {
    agent any
    
    parameters {
        string(
            name: 'TERRAFORM_PATH',
            defaultValue: './terraform',
            description: 'Шлях до Terraform-коду'
        )
        booleanParam(
            name: 'AUTO_APPROVE',
            defaultValue: false,
            description: 'Прапорець для auto-apply'
        )
        choice(
            name: 'ENVIRONMENT',
            choices: ['dev', 'stage', 'prod'],
            defaultValue: 'dev',
            description: 'Оточення (dev, stage, prod)'
        )
    }
    
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
                echo "Environment: ${params.ENVIRONMENT}"
                echo "Terraform Path: ${params.TERRAFORM_PATH}"
                echo "Auto Approve: ${params.AUTO_APPROVE}"
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

