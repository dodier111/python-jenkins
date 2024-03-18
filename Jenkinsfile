pipeline {
    agent any

    stages {
        stage('Checkout Repository') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/dodier111/python-jenkins.git']]])
            }
        }

        stage('Deploy and Run Python Application') {
            steps {
                sh 'pip3 install -r requirements.txt'
                sh 'sudo -u ubuntu /usr/local/bin/pm2 start app.py --interpreter python3'
            }
        }
    }
}
