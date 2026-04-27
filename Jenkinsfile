pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'YOUR_GITHUB_REPO_LINK'
            }
        }

        stage('Build') {
            steps {
                bat 'npm install'
                bat 'npm run build'
            }
        }

        stage('Test') {
            steps {
                bat 'npm test'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t student-app .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 3000:3000 student-app'
            }
        }
    }
}