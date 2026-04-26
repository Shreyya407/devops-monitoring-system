pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        sh 'docker build -t myapp .'
      }
    }

    stage('Deploy') {
      steps {
        sh 'kubectl apply -f k8s/deployment.yaml'
      }
    }
  }
}