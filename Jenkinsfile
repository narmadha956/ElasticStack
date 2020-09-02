pipeline { 
    agent any 
    stages {
        stage('ConfigDisplay') { 
            steps { 
               sh """kubectl config view"""
            }
        }
        stage('Test'){
            steps {
               sh "echo 'Testing...'" 
            }
        }
        stage('Deploy ElasticSearch') {
            steps {
               sh """kubectl apply -f ConfigFiles/elastic.yaml"""            
            }
        }
         stage('Deploy Kibana') {
            steps {
               sh """kubectl apply -f ConfigFiles/apm_es_kibana.yaml"""
            }
        }
    }
}
