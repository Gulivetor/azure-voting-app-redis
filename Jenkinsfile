pipeline {
    agent any

    stages {
        stage('Verify Branch') {
            agent {label 'windows'}
            steps {
                echo "$GIT_BRANCH"
            }
        }
    }
}
