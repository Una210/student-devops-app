pipeline {
    agent any

    stage('Clone') {
         steps {
             git branch: 'main', url: 'https://github.com/Una210/student-devops-app.git'
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