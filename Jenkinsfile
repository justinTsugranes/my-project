pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                checkout scm
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Build Docker Image') {
            steps {
                docker.build('my-image', '.')
            }
        }
        stage('Run Docker Container') {
            steps {
                docker.run('my-image', '-p 8080:3000')
            }
        }
    }
}
