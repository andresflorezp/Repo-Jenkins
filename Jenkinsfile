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
                    sh 'az login --service-principal -u "6a029cca-af89-41da-8332-3260e1ca02e1" -p "7a64dfdc-9220-4823-aa7d-00f428fbf823" -t "50640584-2a40-4216-a84b-9b3ee0f3f6cf"'
                    sh 'terraform plan -out conuplan'
                    sh 'terraform apply -input=false -auto-approve conuplan'
                }
                
            }
        }
    }

}
