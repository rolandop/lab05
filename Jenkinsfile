pipeline {
  agent any
  environment {      
      APPNAME = "lab01"
      IMAGE = "lab01"
      VERSION = 12
      REGISTRY = "rolandop"
      DOCKER_HUB_LOGIN = credentials('dockerhub-rolandop')
  }

  stages { 
      stage('Build Image'){
        steps {
            sh "pwd"
            sh 'docker build -t $REGISTRY/$IMAGE:$VERSION .'
          }
      }
    
      stage('Docker Push to Docker-hub') {
          steps {
              sh 'docker login --username=$DOCKER_HUB_LOGIN_USR --password=$DOCKER_HUB_LOGIN_PSW'
              sh 'docker push $REGISTRY/$APPNAME:$VERSION' 
          }
     }
  }
}
