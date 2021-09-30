pipeline {
  agent any
  
  stages {
    stage('Terraform Init') {
      steps {
        sh "eterraform init -input=false"
      }
    
    stage('Terraform Plan') {
      steps {
        sh "terraform plan -out=tfplan -input=false"
      }
    }
    stage('Terraform Apply') {
      steps {
        input 'Apply Plan'
        sh "terraform apply -input=false tfplan"
      }
    }
  }
}

