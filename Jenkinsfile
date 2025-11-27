pipeline {
    agent any

    stages {
        stage('Install dependencies') {
            steps {
                echo 'Installing dependencies...'
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Run tests') {
            steps {
                echo 'Running Python tests...'
                bat 'pytest --junitxml=results.xml --capture=no'
            }
        }

        stage('Publish results') {
            steps {
                echo 'Publishing test results...'
                junit 'results.xml'
            }
        }
    }

    post {
        always {
            echo 'Sending notification email...'
            mail to: 'anna.fialk@gmail.com',
                 subject: "Jenkins Build ${currentBuild.fullDisplayName}",
                 body: "Build finished. Check results at ${env.BUILD_URL}"
        }
    }
}
