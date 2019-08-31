pipeline {
    agent any
    
    tools {
        nodejs 'NodeJS 4.8.6'
        }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'npm install' 
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'npm run test'
                sh 'npm run coverage'
            }
        }
        stage('Package') {
            steps {
                echo 'Packaging....'
                sh 'npm run package'
                archiveArtifacts artifacts: '**/distribution/*.zip', fingerprint: true
            }
        }
    }
}
