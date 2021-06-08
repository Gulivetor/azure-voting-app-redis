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
                    & $Env:ProgramFiles\Docker\Docker\DockerCli.exe -SwitchLinuxEngine
                    sleep 10
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
