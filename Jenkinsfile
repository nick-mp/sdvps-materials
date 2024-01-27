pipeline {
 agent any
 stages {
  stage('Git') {
   steps {git 'https://github.com/netology-code/sdvps-materials.git'}
  }
  stage('Build') {
   steps {
    /usr/local/go/bin/go test .
    docker build . -t ubuntu-bionic:8082/hello-world:v$BUILD_NUMBER
   }
  }
 }
}
