pipeline {
  agent {
    kubernetes {
        yamlFile 'Vault-namespace-test/build-agent.yaml'
    }
  }
  environment {
        export VAULT_ADDR='https://vault.service.infra-dev.roche.com:8200/'
        export VAULT_TOKEN='hvs.4qtemezVYeBYRMIQ8CB0CCYc'
    	     }
  stages {
     stage('insatlling vault') {
      steps {
        container('buildagent') {
          dir('/'){
          sh "sudo apt update"
          sh "sudo apt install vault" 
          }
         }
        }
      }
      
     stage('create vault namespace') {
      steps {
        container('buildagent') {
          dir('/'){
            sh "ls -lart"
            sh "vault namespace create team1"
           
             }
        }      
      }  
    }
  }
}
