#!groovy
pipeline {
  agent any
  environment {
    AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID')
    AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_KEY')

  }
  stages {
   stage('checkout') {
     steps {

       git branch: 'main', url: 'https://github.com/prakash189/terraform-ec2-pipeline.git'

         }
       }

    stage('Terraform Init') {
     dir(‘dev’)
     steps {
       sh "terraform init"
     }
    
    // stage('Terraform Plan') {
    //   steps {
    //     sh "terraform plan -out=tfplan -input=false"
    //   }
    // }
    // stage('Terraform Apply') {
    //   steps {
    //     input 'Apply Plan'
    //     sh "terraform apply -input=false tfplan"
    //   }
    // }
  }
}

