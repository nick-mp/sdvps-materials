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
  }
  stage('Push') {
   steps {
    sh 'sudo docker login 158.160.13.3:8082 -u admin -p 5d751b18-27d9-432b-962f-5ab6d6b4f278 && docker push ubuntu-bionic:8082/hello-world:v$BUILD_NUMBER && docker logout'
   }
  }  
 }
}
