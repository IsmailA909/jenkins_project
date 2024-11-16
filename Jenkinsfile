pipeline {
    agent any
    environment {
        VIRTUAL_ENV = 'venv'
    }
    stages {
        stage('Setup') {
            steps {
                script {
<<<<<<< HEAD
                    // Forcefully remove the virtual environment if it exists
                    bat "if exist ${VIRTUAL_ENV} rmdir /S /Q ${VIRTUAL_ENV}"
                    // Create a new virtual environment
                    bat "python -m venv ${VIRTUAL_ENV}"
                    // Activate the virtual environment and install dependencies
=======
                    if (!fileExists("${env.WORKSPACE}\\${VIRTUAL_ENV}")) {
                        bat "python -m venv ${VIRTUAL_ENV}"
                    }
>>>>>>> 50ca9e1b9405e1a18bfacb8fc34cb4e7cb8de5bd
                    bat "${VIRTUAL_ENV}\\Scripts\\activate && pip install -r requirements.txt"
                }
            }
        }
        stage('Lint') {
            steps {
                script {
<<<<<<< HEAD
                    // Run flake8 for linting
=======
>>>>>>> 50ca9e1b9405e1a18bfacb8fc34cb4e7cb8de5bd
                    bat "${VIRTUAL_ENV}\\Scripts\\activate && flake8 app.py"
                }
            }
        }
        stage('Test') {
            steps {
                script {
<<<<<<< HEAD
                    // Run pytest for testing
=======
>>>>>>> 50ca9e1b9405e1a18bfacb8fc34cb4e7cb8de5bd
                    bat "${VIRTUAL_ENV}\\Scripts\\activate && pytest"
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
<<<<<<< HEAD
                    // Placeholder for deployment logic
=======
                    // Deployment logic, e.g., pushing to a remote server
>>>>>>> 50ca9e1b9405e1a18bfacb8fc34cb4e7cb8de5bd
                    echo "Deploying application..."
                }
            }
        }
    }
    post {
        always {
<<<<<<< HEAD
            // Clean the workspace after build
=======
>>>>>>> 50ca9e1b9405e1a18bfacb8fc34cb4e7cb8de5bd
            cleanWs()
        }
    }
}
