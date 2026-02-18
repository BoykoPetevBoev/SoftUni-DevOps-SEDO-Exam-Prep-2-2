pipeline{
    agent {
        docker {
            image 'mcr.microsoft.com/dotnet/sdk:8.0'
        }
    }
    stages{
        stage("Restore dependencies"){
            when {
                expression {
                    env.GIT_BRANCH == 'origin/main'
                }
            }
            steps{
                sh "dotnet restore"
            }
        }
        stage("Build the project"){
            when {
                expression {
                    env.GIT_BRANCH == 'origin/main'
                }
            }
            steps{
                sh "dotnet build --no-restore"
            }
        }
        stage("Run the tests"){
            when {
                expression {
                    env.GIT_BRANCH == 'origin/main'
                }
            }
            steps{
                sh "dotnet test --no-build --verbosity normal"
            }
        }
    }
}