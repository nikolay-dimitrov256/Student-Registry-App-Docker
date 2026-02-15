pipeline{
    agent any
    stages{
        stage("Install dependencies"){
            steps{
                bat "npm install"
            }
        }
        failfast true
        parallel {
            stage("Run security tests"){
                steps{
                    bat "npm audit"
                }
            }
            stage("Run tests"){
                steps{
                    bat "npm test"
                }
            }
        }
    }
}