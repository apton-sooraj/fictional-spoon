pipeline {
  agent  any  
  
  environment {
    imageId = 'use-name/image-name:1.$BUILD_NUMBER'
    docker_registry = 'your_docker_registry'
    docker_creds = credentials('your_docker_registry_creds')
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
