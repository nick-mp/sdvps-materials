pipeline {
 agent any
 stages {
  stage('Git') {
   steps {git 'https://github.com/netology-code/sdvps-materials.git'}
  }
  stage('Test') {
   steps {
    sh 'go test .'
   }
  }
  stage('Build') {
   steps {
    sh 'docker build . -t ubuntu-bionic:8082/hello-world:v$BUILD_NUMBER'
   }
   stage('Push') {
   steps {
    sh 'docker login 127.0.0.1:8123 -u admin -p admin123 && docker push ubuntu-bionic:8082/hello-world:v$BUILD_NUMBER && docker logout'   }
   }
  }
 }
}
