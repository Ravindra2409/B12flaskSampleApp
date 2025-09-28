pipeline {
    agent any

    environment {
        VENV = 'venv'
    }

    stages {
        stage('Build') {
            steps {
                sh 'python3 -m venv $VENV'
                sh './$VENV/bin/pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                sh './$VENV/bin/pip install pytest'
                sh './$VENV/bin/pytest tests/'
            }
        }

        stage('Deploy') {
            when {
                expression { currentBuild.result == null || currentBuild.result == 'SUCCESS' }
            }
            steps {
                sh 'echo "Deploying to staging..."'
                // Add deployment script here
            }
        }
    }

    post {
        success {
            mail to: 'your-email@example.com',
                 subject: "Build Success: ${env.JOB_NAME}",
                 body: "The build ${env.BUILD_NUMBER} succeeded."
        }
        failure {
            mail to: 'your-email@example.com',
                 subject: "Build Failed: ${env.JOB_NAME}",
                 body: "The build ${env.BUILD_NUMBER} failed."
        }
    }
}
