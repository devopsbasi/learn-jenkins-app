pipeline {
    agent any
    
    stages {

        stage('Build') {
            agent {
                docker {
                    image 'node:22-alpine'
                    args '-u root'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm  --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}