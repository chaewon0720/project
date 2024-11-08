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
        mv image/Dockerfile . && mv image/index.html .
        sudo docker build -t chaewon0720/portal:welcome .
        sudo docker push chaewon0720/portal:welcome
        '''
      }
    }
    stage('deploy and service') {
      steps {
        sh '''
        pwd
        ansible-playbook /var/lib/jenkins/node_ansible.yml
        ansible-playbook /var/lib/jenkins/master_ansible.yml
        '''
      }
    }
  }
}
