pipeline {
    agent any

    stages {
        stage('github-clone') {
            steps {
                git branch: 'main', credentialsId: 'github_token', url: 'https://github.com/chaewon0720/project.git'
            }
        }

        // stage...
    }
}
