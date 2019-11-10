pipeline {

    agent any 

    stages {
        stage('Init'){
            steps{
                dir('./TerraformLAB'){
                    sh 'terraform init'
                }
            }
        }
        stage('Apply') {
            steps {
                dir('./TerraformLAB'){
                    sh 'az login --service-principal -u $ARM_CLIENT_ID -p $ARM_CLIENT_SECRET -t $ARM_TENANT_ID'
                    sh 'terraform plan -out conuplan'
                    sh 'terraform apply -input=false -auto-approve conuplan'
                }
                
            }
        }
    }

}
