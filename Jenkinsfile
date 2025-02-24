pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/karthikeya964/newrepo5.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                    python -m venv venv
                    . venv/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                    . venv/bin/activate
                    pytest tests/
                '''
            }
        }

        stage('Build Artifact') {
            steps {
                echo 'Building the project...'
            }
        }

        stage('Archive Artifact') {
            steps {
                echo 'Archiving artifacts...'
            }
        }
    }
}
