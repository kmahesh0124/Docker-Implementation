pipeline {
    agent any

    stages {
        stage('Pre Cleanup Workspace') {
            steps {
                script {
                    sh label: '', script: 'docker system prune -f > /dev/null 2>&1'
                    cleanWs()
                }
            }
        }
        stage('Checkout SCM') {
            steps {
                script {
                    git credentialsId: 'githubid', url: ''
                }
            }
        }
        stage('NPM Install') {
            steps {
                script {
                    sh label: '', script: 'npm install'
                }
            }
        }
        stage('Docker Build') {
            steps {
                script {
                   sh label: '', script: 'docker build -t mahesh .'
                }
            }
        }
        stage('Docker Push to Docker Hub') {
            steps {
                script {
                    
                    }
                }
            }
        }
        stage('Post Cleanup Workspace') {
            steps {
                script {
                    sh label: '', script: 'docker system prune -f > /dev/null 2>&1'
                    cleanWs()
                }
            }
        }
    }
}