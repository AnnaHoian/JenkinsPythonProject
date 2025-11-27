pipeline {
    agent any

    stages {
        stage('Install dependencies') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Run tests') {
            steps {
                bat 'pytest --junitxml=results.xml'
            }
        }

        stage('Publish results') {
            steps {
                junit 'results.xml'
            }
        }
    }

    post {
        always {
            mail to: 'anna.fialk@gmail.com',
                 subject: "Jenkins Build ${currentBuild.fullDisplayName}",
                 body: "Build finished. Check results at ${env.BUILD_URL}"
        }
    }
}
