pipeline {
    agent any
    environment {
        VIRTUAL_ENV = 'venv'
    }
    stages {
        stage('Setup') {
            steps {
                script {
                    // Forcefully remove the virtual environment if it exists
                    bat "if exist ${VIRTUAL_ENV} rmdir /S /Q ${VIRTUAL_ENV}"
                    // Create a new virtual environment
                    bat "python -m venv ${VIRTUAL_ENV}"
                    // Activate the virtual environment and install dependencies
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
        stage('Deploy') {
            steps {
                script {
                    // Placeholder for deployment logic
                    echo "Deploying application..."
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
