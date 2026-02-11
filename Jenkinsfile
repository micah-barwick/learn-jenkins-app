pipeline {
    agent any

    stages {
        stage('Build') {
            agent{
                docker{
                    reuseNode true
                    image 'node:18-alpine' 
                }
            }
            steps {
                sh '''
                ls -la
                node --version
                npm --version
                npm ci
                npm run build
                '''
            }
        }
        stage('Test') {
            agent{
                docker{
                    reuseNode true
                    image 'node:18-alpine' 
                }
            }steps {
                sh '''
                echo 'Test Stage'
                ls -la
                npm test
                '''
            }
        }
    }
}