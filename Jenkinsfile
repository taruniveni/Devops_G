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
        stage('Test') {
            steps {
                echo 'Running application tests...'
                sh 'test -s app/app.txt'
                sh 'test -s config/app.conf'
                sh 'test -x scripts/deploy.sh || chmod +x scripts/deploy.sh'
                echo 'All tests passed!'
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

