pipeline {

    agent any

    stages {

        stage('Pull Code') {
            steps {
                git 'https://github.com/npk-aws/Flask-and-MongoDB.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                python3 -m venv venv
                venv/bin/pip install -r requirements.txt
                '''
            }
        }

        stage('Deploy Flask') {
            steps {
                sh 'sudo systemctl restart flask'
            }
        }

    }
}
