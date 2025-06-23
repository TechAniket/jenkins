pipeline {
    agent any

    stages {
        stage('Run Docker Compose') {
            steps {
                dir('jenkins/jenkins') {
                    sh 'docker-compose up -d --build'
                }
            }
        }
    }

    post {
        always {
            dir('jenkins/jenkins') {
                sh 'docker-compose down || true'
            }
        }
    }
}
