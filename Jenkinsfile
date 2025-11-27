pipeline {
    agent any

    stages {
        stage('Check Python') {
            steps {
                echo 'Step 1: Checking Python version'
                bat '"C:\\Users\\Anna\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" --version'
            }
        }

        stage('Run tests') {
            steps {
                echo 'Step 2: Running pytest tests'
                bat '"C:\\Users\\Anna\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" -m pytest --junitxml=results.xml'
            }
        }

        stage('Publish results') {
            steps {
                echo 'Step 3: Publishing test results in Jenkins'
                junit 'results.xml'
            }
        }
    }

    post {
        always {
            echo 'Step 4: Email step (needs SMTP configured)'
            // mail to: 'InsertYour@Mail.Here',
            //      subject: "Jenkins Build ${currentBuild.fullDisplayName}",
            //      body: "Build finished. Check results at ${env.BUILD_URL}"
        }
    }
}
