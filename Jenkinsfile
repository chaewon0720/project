pipeline {
  agent any
  stages {
    stage('git scm update') {
      steps {
        git url: 'https://github.com/chaewon0720/project.git', branch: 'main'
      }
    }
    stage('docker build and push') {
      steps {
        sh '''
        sudo docker build -t chaewon0720/portal:welcome /image .
        sudo docker push chaewon0720/portal:welcome
        '''
      }
    }
    stage('deploy and service') {
      steps {
        sh '''
        pwd
        '''
      }
    }
  }
}
