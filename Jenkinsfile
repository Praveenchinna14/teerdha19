
pipeline{
    agent any
    stages {
        stage('aws'){
            steps  {

        withCredentials([aws(accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws-cred', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY')]) {
    // some block
   }
 }           
}
        stage('dev'){

      steps  {
            sh '''
            terraform init
            terraform apply -var-file=dev.tfvars -auto-approve
            '''
            }
        }
        stage('prod'){
            steps {
                sh '''
                terraform init
                terraform apply -var-file=prod.tfvars -auto-approve
                '''
            }
        }
        stage('test'){
            steps {
                sh '''
                terraform init
                terraform apply -var-file=test.tfvars -auto-approve
                '''
            }
        }  
    }
}
