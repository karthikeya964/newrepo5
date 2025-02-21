pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git url:'https://github.com/karthikeya964/newrepo5.git',branch:'main'
            }
        }

        stage('Install Dependencies') {
    steps {
        sh 'python --version'
        sh 'pip --version'
        sh 'pip install -r requirements.txt'
    }
}


        stage('Run Tests') {
            steps {
                sh 'pytest tests/'
            }
        }

        stage('Build Artifact') {
    steps {
        sh 'python setup.py sdist bdist_wheel'
    }
}

       stage('Archive Artifact') {
    steps {
        archiveArtifacts artifacts: '**/dist/*.tar.gz', fingerprint: true
    }
}

    }
}
