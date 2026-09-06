pipeline {

    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                sh '''
                    python3 -m venv venv
                    ./venv/bin/pip install -r requirements.txt
                '''
            }
        }

        stage('Deploy Flask') {
            steps {
                sh '''
                    sudo systemctl restart flask
                    sudo systemctl status flask --no-pager
                '''
            }
        }
    }
}
