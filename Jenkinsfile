pipeline {
    agent { label 'agent' }

    stages {
        stage('clone') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t fireimg .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker run -itd --name vijcon -p "2020:80" fireimg'
            }
        }
    }
}
