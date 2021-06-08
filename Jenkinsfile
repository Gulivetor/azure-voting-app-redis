pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Goodbye') {
            steps {
                echo 'Goodbye'
            }
        }
        stage('pwsh Hello') {
            agent {lable 'windows'}
            steps {
                powershell 'Write-Output "Hello PowerShell!"'
            }
        }
    }
}
