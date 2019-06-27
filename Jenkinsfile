pipeline {
  agent any
  stages {
    stage('PipelineStarted') {
      steps {
        echo 'This pipeline just started'
      }
    }
    stage('dockerBuildImage') {
      steps {
        script {
          dockerImage = docker.build("ajaysheoran2323/docker-nginx:$BUILD_NUMBER","-f dockerfile/MyDockerFile .")
        }

      }
    }
    stage('pipeline completed') {
      steps {
        echo 'completed'
      }
    }
  }
}