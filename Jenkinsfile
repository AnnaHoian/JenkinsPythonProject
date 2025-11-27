pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Step 1: Checkout code from Git (simulated)'
            }
        }

        stage('Install dependencies') {
            steps {
                echo 'Step 2: Installing dependencies (simulated, skipped)'
            }
        }

        stage('Run tests') {
            steps {
                echo 'Step 3: Running tests (simulated)'
                bat 'echo Tests executed successfully'
            }
        }

        stage('Publish results') {
            steps {
                echo 'Step 4: Publishing test results (simulated)'
            }
        }
    }

    post {
        always {
            echo 'Step 5: Email notification (simulated)'
            // mail to: 'InsertYour@Mail.Here', subject: "...", body: "..."
        }
    }
}
