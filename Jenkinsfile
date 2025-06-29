pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Restore Dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build the project') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Run Tests for the project') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
