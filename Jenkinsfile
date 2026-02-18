pipeline{
    agent any
    stages{
        stage("Restore dependencies"){
            when {
                anyOf {
                    branch 'main'
                    branch 'origin/main'
                }
            }
            steps{
                bat "dotnet restore"
            }
        }
        stage("Build the project"){
            when {
                anyOf {
                    branch 'main'
                    branch 'origin/main'
                }
            }
            steps{
                bat "dotnet build --no-restore"
            }
        }
        stage("Run the tests"){
            when {
                anyOf {
                    branch 'main'
                    branch 'origin/main'
                }
            }
            steps{
                bat "dotnet test --no-build --verbosity normal"
            }
        }
    }
}