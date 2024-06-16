pipeline {
    agent any
    
    parameters {
        string(name: 'BRANCH', defaultValue: 'main', description: 'Branch to deploy')
    }
    
    stages {
        stage('Checkout') {
            steps {
                git branch: params.BRANCH, url: 'https://github.com/symfony/demo.git'
            }
        }
        
        stage('Install dependencies') {
            steps {
                sh 'composer install --no-dev --optimize-autoloader'
            }
        }
        
        stage('Prepare release') {
            steps {
                sh 'rm -rf release'
                sh 'mkdir release'
                sh 'rsync ./* release --recursive --exclude .git --exclude release'
            }
        }
        
        stage('Switch symlink') {
            steps {
                sh 'ln -sfn $WORKSPACE/release /var/www/symfony_demo/current'
            }
        }
        
        stage('Clear cache') {
            steps {
                sh 'rm -rf /var/www/symfony_demo/current/var/cache/*'
            }
        }
    }
}
