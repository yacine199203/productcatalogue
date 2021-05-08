pipeline {
  agent any
  stages {
    stage('Test mvn') {
      steps {
         sh 'mvn test'
         sh 'mvn package'
      }
    }  
    
    stage('compilation') {
      steps {
         sh 'mvn package'
      }
    } 
    
    stage ('Publication du binaire') { 
      steps { 
        sh "curl -u admin:123456789 --upload-file target/*.war 'http://http://10.10.20.30:8081/productcatalogue/app${BUILD_NUMBER}.war'" 
 } 
 } 
  }
}
