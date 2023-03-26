pipeline {
    agent any

    stages {
        stage('git') {
            steps {
                 git branch: 'main', url: 'https://github.com/GlooK137/UCS_DSO_DZ1'
            }
        }
        stage('docker stop') {
            steps {
                sh 'sudo docker stop nodejs || echo 0 >> /dev/null'
                sh 'sudo docker rm nodejs  || echo 0 >> /dev/null'
            }
        }
        stage('docker start') {
            steps {
                sh 'sudo docker build -t node-app .'
                sh 'sudo docker run -p 3000:3000 --name nodejs -d node-app'
            }
        }
    }
}
