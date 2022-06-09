pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/jung2uncan/gitOps_k8s_book.git will replace by sed command before RUN
        git url: 'https://github.com/jung2uncan/gitOps_k8s_book.git', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}