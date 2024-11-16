pipeline {
    agent any
    environment {
        VIRTUAL_ENV = 'venv'
    }
    stages {
        stage('Setup') {
            steps {
                script {
                    // Remove existing virtual environment and recreate
                    bat "if exist ${VIRTUAL_ENV} rmdir /S /Q ${VIRTUAL_ENV}"
                    bat "python -m venv ${VIRTUAL_ENV}"
                    bat "${VIRTUAL_ENV}\\Scripts\\activate && pip install -r requirements.txt"
                }
            }
        }
        stage('Lint') {
            steps {
                script {
                    // Run flake8 for linting
                    bat "${VIRTUAL_ENV}\\Scripts\\activate && flake8 app.py"
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Run pytest for testing
                    bat "${VIRTUAL_ENV}\\Scripts\\activate && pytest"
                }
            }
        }
        stage('Coverage') {
            steps {
                script {
                    // Run coverage to generate coverage reports
                    bat "${VIRTUAL_ENV}\\Scripts\\activate && coverage run -m pytest"
                    bat "${VIRTUAL_ENV}\\Scripts\\activate && coverage report"
                    bat "${VIRTUAL_ENV}\\Scripts\\activate && coverage html"
                }
            }
        }
        stage('Security Scan') {
            steps {
                script {
                    // Run Bandit for security scanning
                    bat "${VIRTUAL_ENV}\\Scripts\\activate && bandit -r ."
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    // Placeholder for deployment logic
                    echo "Deploying application..."
                    // Example deployment: copy files to a remote directory
                    bat "xcopy /E /I . \\remote\\server\\path"
                }
            }
        }
    }
    post {
        always {
            // Clean the workspace after build
            cleanWs()
        }
    }
}
