pipeline {
    agent {
        node {
            label 'docker-agent-alpine-python'
            }
      }
    stages {
        stage('Build') {
            steps {
                echo "Building the app"
                sh '''
                cd my-python-app
                python3 -m venv .venv
                source .venv/bin/activate
                python3 -m pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing the app"
                sh '''
                cd my-python-app
                python3 hello.py
                python3 hello.py --name=spider-man
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver the app'
                sh '''
                echo "Delivering application"
                '''
            }
        }
    }
}