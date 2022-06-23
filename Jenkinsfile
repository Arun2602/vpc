pipeline {
    agent {
        label 'terraform'
    }
    
    stages {
        stage('AWS credentials & terraform init') {
            steps {
                withCredentials([[
                    $class: 'AmazonWebServicesCredentialsBinding',
	                credentialsId: 'aws-configure-terraform',
	                accessKeyVariable: 'AWS_ACCESS_KEY_ID',
	                secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
	                    
	                    sh 'terraform init'
                }  
            }
        }
        
        stage('terraform apply') {
            steps {
                sh 'terraform apply -auto-approve'
            }
        }
    }
}
