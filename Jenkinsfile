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
                    sh 'az login -u "andres.florez-p@mail.escuelaing.edu.co" -p "970813Leo.$" 
                    sh 'terraform init -input=false'
                    sh 'terraform plan -out=tfplan -input=false'
                    sh 'terraform apply -input=false tfplan'
                }
                
            }
        }
    }

}
