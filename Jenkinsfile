pipeline {
    agent any
    
    environment {
        DOTNET_ROOT = '/usr/local/share/dotnet'
        PATH = "/usr/local/share/dotnet:${env.PATH}"
    }
    
    stages {
        stage('Restore dependencies') {
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build solution') {
            steps {
                sh 'dotnet build --no-restore'
            }
        }
        stage('Run tests') {
            steps {
                sh 'dotnet test --no-build'
            }
        }
    }
}