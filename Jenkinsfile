pipeline {
    agent any

    stages {
        stage('Setup and Run') {
            steps {
                sh '''
                    # Set up the virtual environment
                    python -m venv venv
                    . venv/bin/activate
                    
                    # Install dependencies
                    pip install --upgrade pip
                    pip install -r requirements.txt

                    # Run tests
                    pytest tests/

                    # Build Artifact
                    echo "Building the project..."

                    # Archive Artifact
                    echo "Archiving artifacts..."
                '''
            }
        }
    }
}
