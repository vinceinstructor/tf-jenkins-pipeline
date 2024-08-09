pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    }
    stages {
        // stage('Checkout') {
        //     steps {
        //         git branch: 'main' url: 'https://github.com/vinceinstructor/terraform-project.git'
        //     }
        // }
        // stage('Terraform install') {
        //     steps {
        //         sh 'snap install terraform --classic'
        //     }
        // }
        stage('Terraform Init') {
            steps {
                sh ' terraform init'
            }
        }
         stage(' Terraform Format') {
            steps {
                sh 'terraform fmt '
            }
        }
         stage(' Terraform validate') {
            steps {
                sh 'terraform validate '
            }
        }
        stage(' Terraform Plan') {
            steps {
                sh 'terraform plan '
            }
        }
        stage(' Terraform Apply') {
            steps {
                sh 'terraform apply -auto-approve'
            }
        }
        stage('Terraform destroy') {
            steps {
                sh 'terraform destroy -auto-approve'
            }
        }
    }
}