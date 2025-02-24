pipeline {
    agent any

    stages {
        stage('Setup and Run') {
            steps {
                sh '''
                    python -m venv venv
                    . venv/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt

                    # Run tests
                    pytest newrepo5/tests/

                    # Build Artifact
                    echo "Building the project..."

                    # Archive Artifact
                    echo "Archiving artifacts..."
                '''
            }
        }
    }
}
