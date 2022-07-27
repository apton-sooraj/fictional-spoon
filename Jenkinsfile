pipeline {
  agent  any  
    stages {
    stage('Docker build') {
      steps {
        sh "docker build --no-cache --force-rm -t test ."
      }
    }
    stage('Clean') {
      steps{
        sh "docker rmi test"
      }
    }
  }
}
