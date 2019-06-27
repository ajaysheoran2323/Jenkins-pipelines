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
    stage('DEPLOYTOK8S') {
      steps {
        script {
          kubernetesDeploy(kubeconfigId: 'kubernetes',

          configs: 'K8sDeployment.yaml',
          enableConfigSubstitution: false,
          secretNamespace: 'devops',
          secretName: 'devops'
        )
      }

    }
  }
  stage('PipelineEnded') {
    steps {
      echo 'Pipeline successful'
    }
  }
}
}