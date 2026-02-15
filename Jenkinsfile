pipeline{
    
    agent any

    stages{
        stage("Install dependencies"){
            steps{
                bat "npm install"
            }
        }
        stage("Run tests and security checks") {
            failFast true
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
}