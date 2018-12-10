node {
  def mvnHome
  
  stage('Preparation') { // for display purposes
     // Get some code from a GitHub repository
     git 'https://github.com/johndavid93/import.git'
  }
  
  stage('Importar') {
 //COMANDO PARA SUBIR ARCHIVO A DATAPOWER
        sh 'curl –H "Content-Type: text/xml" --data-binary @importardatapower.xml https://192.168.1.74:5550/service/mgmt/current -u admin:admin123 -k'
  }
  
  stage('Results') {
sh""
     junit '**/target/surefire-reports/TEST-*.xml'
     archive 'target/*.jar'
  }
}
