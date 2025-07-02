pipeline {
  agent any
  stages {
    stage('Clone Repo') {
      steps {
        git branch: 'main', url: 'https://github.com/jugaduraj/test.git'
      }
    }
    stage('Clean Old Container') {
      steps {
        sh 'docker rm -f webapp || true'
      }
    }
    stage('Build Docker Image') {
      steps {
        sh 'docker build -t my-html-app .'
      }
    }
    stage('Run Docker Container') {
      steps {
        sh 'docker run -d -p 80:80 --name webapp my-html-app'
      }
    }
  }
}
