pipeline {
    agent any

    stages {
        stage('Checkout') {
            when { branch 'main' }
            steps {
                checkout scm
            }
        }

        stage('Setup .NET') {
            when { branch 'main' }
            steps {
                bat 'dotnet --version'
            }
        }

        stage('Restore dependencies') {
            when { branch 'main' }
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            when { branch 'main' }
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Test') {
            when { branch 'main' }
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
