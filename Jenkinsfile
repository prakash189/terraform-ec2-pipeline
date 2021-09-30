pipeline {
  agent any
  environment {
    AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID')
    AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_KEY')
  }
  stages {
    stage('Terraform Init') {
      steps {
        sh "terraform init -input=false"
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

