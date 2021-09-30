pipeline {
  parameters {
    password (name: 'AKIARCJIKTQOA63XZZWP')
    password (name: 'ids8CdP0PkygM0j68j91MqsbV3HnwRLLo7vEovQ2')
  }
  environment {
    AWS_ACCESS_KEY_ID = "${params.AWS_ACCESS_KEY_ID}"
    AWS_SECRET_ACCESS_KEY = "${params.AWS_SECRET_ACCESS_KEY}"
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

