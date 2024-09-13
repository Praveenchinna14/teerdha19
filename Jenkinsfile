pipeline{
    agent any
    environment {
        AWS_ACCESS_KEY_ID     = credentials('aws-cred')
        AWS_SECRET_ACCESS_KEY = credentials('aws-cred')
    }
    stages {
        stage('dev'){

      steps  {
            sh '''
            terraform init
            terraform plan -out=dev.tfplan
            terraform apply dev.tfplan
            '''
            }
        }
        stage('prod'){

        steps  {    
          sh '''
            terraform init
            terraform plan -out=Prod.tfplan
            terraform apply Prod.tfplan
            ''' 
        }
            }
        }
    }
}
