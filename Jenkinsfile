pipeline {
    agent {label 'windows'}

    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        }
        stage('Docker Build') {
            steps {
                powershell 'docker images -a'
                powershell """
                    [Environment]::SetEnvironmentVariable(\"LCOW_SUPPORTED\", \"1\", \"Machine\")
                    Restart-Service docker
                """
                powershell """
                    cd azure-vote/
                    docker images -a
                    docker build -t jenkins-pipeline .
                    docker images -a
                    cd ..
                """
            }
        }
    }
}
