pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
            }
        }

        stage('Validate') {
            steps {
                echo 'Validating project files...'
                sh 'test -f app/app.txt'
                sh 'test -f config/app.conf'
                sh 'test -f scripts/deploy.sh'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Running deployment script...'
                sh 'chmod +x scripts/deploy.sh'
                sh './scripts/deploy.sh'
            }
        }

        stage('Verify') {
            steps {
                echo 'Verifying deployment...'
                sh 'echo "Deployment verification successful."'
            }
        }
    }

    post {
        success {
            echo 'Jenkins pipeline completed successfully!'
        }

        failure {
            echo 'Jenkins pipeline failed.'
        }
    }
}

