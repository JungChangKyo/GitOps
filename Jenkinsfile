pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/JungChangKyo/GitOps.git will replace by sed command before RUN TEST
        git url: 'https://github.com/JungChangKyo/GitOps.git', branch: 'main'
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
