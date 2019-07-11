pipeline {
  agent any
  stages {
    stage('stage1') {
      steps {
        echo 'Pipeline started'
      }
    }
    stage('Build-Image') {
      steps {
        script {
          dockerImage = docker.build("ajaysheoran2323/docker-nginx:$BUILD_NUMBER","-f dockerfile/MyDockerFile .")
          dockerImage.push()
        }

      }
    }
  }
}