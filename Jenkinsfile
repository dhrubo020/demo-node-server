pipeline {
  agent {
    docker {
      image 'jenkins/jenkins:lts'
      args '-v /var/run/docker.sock:/var/run/docker.sock'
    }
  }
  stages {
    stage('Build and Push Docker Image') {
      steps {
        sh 'docker build -t demo-server .'
        sh 'docker run -d -it -p 5000:5000 --name=demo-server demo-server'
      }
    }
  }
}
