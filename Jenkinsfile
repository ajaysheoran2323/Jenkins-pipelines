pipeline {
  agent any
  stages {
    stage('stage1') {
      steps {
        echo 'Pipeline started'
      }
    }
    stage('Docker build') {
      steps {
        script {
          dockerImage = docker.build("ajaysheoran2323/docker-nginx:$BUILD_NUMBER","-f dockerfile/MyDockerFile .")
        }

      }
    }
    stage('Dockerpush') {
      steps {
        script {
          docker.withRegistry("", 'dockerhub'){
            dockerImage.push()
          }
        }

      }
    }
    stage('complete') {
      steps {
        echo 'pipeline completed.'
      }
    }
  }
}