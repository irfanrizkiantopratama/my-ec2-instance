pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/irfanrizkiantopratama/my-ec2-instance']]])
            }
        }
        
        stage ("terraform init") {
            steps {
                sh 'terraform init'
            }
        }
        
        stage ("terraform Action") {
            steps {
                echo "Terraform action is --> ${action}"
                sh 'terraform ${action} --auto-approve' 
           }
        }
    }
}
