pipeline { 
    environment {
     registry = "hugdora/devops-pipe"
     registryCredential = ‘c7094805-3454-402a-8986-46fb33e0b264
 agent any
 tools {
  maven 'M2_HOME'
 }
 stages {
  stage('Build'){
   steps {
    sh 'mvn clean'
    sh 'mvn install'
    sh 'mvn package'
         }
  }
   stage('test'){
   steps {
    echo "test step"
    sh 'mvn test'
         }
  }
   stage('Deploy'){
    steps{
        script {
          docker.build registry + ":tagname"
         }
  }
   stage('docker'){
   steps {
    echo "docker step"
    sleep 10
   }
  }
 }
}
