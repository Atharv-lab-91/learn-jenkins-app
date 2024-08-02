pipeline{
    agent any
    stages{
        stage('build'){
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps{
                sh '''
                  ls -la
                  npm --version
                  node --version
                  npm ci
                  npm run build
                '''
            }
        }
        stage('Test'){
            steps{
                sh 'echo "Hi from test stage"'
            }
        }
    }
}