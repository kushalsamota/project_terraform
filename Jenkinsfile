pipeline {
    agent any
    tools {
  terraform 'terraform'
}
stages {
    stage('gitcheckout'){
        steps {
         git branch: 'main', credentialsId: 'd91e2351-22d1-4c44-af82-d91ec2cf54e2', url: 'https://github.com/kushalsamota/project_terraform.git'   
        }
    }
    stage('Terraform Initialization'){
        steps {
            sh 'terraform init'
        }
    }
    stage('Terraform Showing Plan'){
        steps {
           sh 'terraform plan' 
        }
    }
    stage('Provisioning Resources'){
        steps {
            sh 'terraform destroy --auto-approve'
        }
    }
}
}
