pipeline {
    agent any

    environment {
        VENV_PATH = "${WORKSPACE}/venv"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/karthikeya964/newrepo5.git'
            }
        }

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
                    # Simulate build (replace with your actual build command)
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
