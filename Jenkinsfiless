pipeline {
    agent any
    tools {
      terraform 'TerraformV12'
    }

    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', credentialsId: '7beec0a5-a26b-4a36-8b54-f7eda616b661', url: 'https://github.com/edmundtetteh/Project-Edmund.git'
            }
        }
        stage('Terraform init') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Terraform Apply') {
            steps {
                sh 'terraform apply --auto-approve'
            }
        }
    }
}
