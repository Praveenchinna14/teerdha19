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
        stage('prod'){
            steps {
                sh '''
                terraform init
                terraform apply -var-file=prod.tfvars -auto-approve
                '''
            }
        }
    }
}
