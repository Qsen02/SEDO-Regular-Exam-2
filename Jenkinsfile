pipeline{
    agent any

    stages{
        stage("Checkout repo"){
            steps{
                checkout scm 
            }
        }
        stage("Restore"){
            steps{
                bat "dotnet restore"
            }
        }
        stage("Build"){
            steps{
                bat "dotnet build --no-restore"
            }
        }
        stage("Test"){
            steps{
                bat "dotnet test"
            }
        }
    }
    post{
        always{
            echo "always"
        }
        success{
            echo "pipeline executed successfully"
        }
        failure{
            echo "pipeline execution failed"
        }
    }
}