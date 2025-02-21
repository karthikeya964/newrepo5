pipeline {
    agent any

    environment {
        VENV_PATH = "${WORKSPACE}/venv"
    }

    stages {
        stage('Install Dependencies') {
            steps {
                sh '''
                    #!/bin/bash
                    python3 -m venv venv
                    source venv/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                    #!/bin/bash
                    source venv/bin/activate
                    pytest tests/
                '''
            }
        }

        stage('Build Artifact') {
            steps {
                echo 'Building the project...'
                sh '''
                    mkdir -p target
                    echo "Build successful" > target/output.txt
                '''
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: '**/target/*.*', allowEmptyArchive: true
            }
        }
    }
}
