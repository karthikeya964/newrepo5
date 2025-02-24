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

                    # Run tests (commented until tests are available)
                    pytest newrepo5/python/tests/


                    # Build Artifact
                    echo "Building the project..."

                    # Archive Artifact
                    echo "Archiving artifacts..."
                '''
            }
        }
    }
}
