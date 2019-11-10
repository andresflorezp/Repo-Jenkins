pipeline {

    agent any 

    stages {
        stage('Init'){
            steps{
                dir('/tmp/TerraformLab'){
                    sh 'terraform init'
                }
            }
        }
        stage('Apply') {
            steps {
                dir('/tmp/TerraformLab'){
                    sh 'az login --service-principal -u $ARM_CLIENT_ID -p $ARM_CLIENT_SECRET -t $ARM_TENANT_ID' 
                    sh 'terraform plan -out=tfplan -input=false'
                    sh 'terraform apply -input=false tfplan'
                }
                
            }
        }
    }

}
