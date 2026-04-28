pipeline {
    agent any

    environment {
        VERCEL_TOKEN = credentials('vercel-token') 
    }

    stages {
        stage('npm Install') {
            steps {
                echo 'Installing dependencies...'
                bat 'npm install'
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                bat 'npm run build'
            }
        }
        stage('Test') {
            steps {
                echo 'Skipping tests...'
            }
        }
        stage('Deploy to Vercel') {
            steps {
                echo 'Deploying to Vercel...'
                // Add your deployment commands here, e.g., using Vercel CLI
                bat 'npx vercel . --prod --yes --token=%VERCEL_TOKEN%'
            }
        }
    }
}