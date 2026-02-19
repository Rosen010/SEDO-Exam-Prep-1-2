pipeline {
    agent any
    stages {
        stage('Restore dependencies') {
            when {
                anyof {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                bat 'dotnet restore'
            }
        }
        stage("Build the app") {
            when {
                anyof {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage("Run tests") {
            when {
                anyof {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}