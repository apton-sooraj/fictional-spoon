pipeline {
  agent  any  
  
  environment {
    imageId = 'sooraj/image-name:1.$BUILD_NUMBER'
    docker_registry = 'dockerhub.io'
  }
  stages {
    stage('Docker build') {
      steps {
        sh "docker build --no-cache --force-rm -t ${imageId} ."
      }
    }
    stage('Clean') {
      steps{
        sh "docker rmi ${imageId}"
      }
    }
  }
}
