pipeline {
  agent any
  // any, none, label, node, docker, dockerfile, kubernetes
  tools {
    maven 'my_maven'
  }
  environment {
    gitName = 'ITTAEKGEUN'
    gitEmail = 'xorrms007@naver.com'
    githubCredential = 'git_cre'
    dockerHubRegistry = '10.7.7.11/sbimage'
    githubWeb = 'https://github.com/ITTAEKGEUN/sb_code.git'
  }
  stages {
    stage('Checkout Github') {
      steps {
          checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: githubCredential, url: 'githubWeb']]])
          }
      post {
        failure {
          echo 'Repository clone failure'
        }
        success {
          echo 'Repository clone success'  
        }
      }
    }

    
  }
}

