pipeline {
    agent {
        label 'terraform'
    }
    
     stages {
        stage('AWS Credentials & terraform') {
            steps {
                withCredentials([[
                    $class: 'AmazonWebServicesCredentialsBinding',
	       		credentialsId: 'dcbbf8b7-feee-4725-9d66-d5f9be42c9ff',
	                accessKeyVariable: 'AWS_ACCESS_KEY_ID',
	                secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
	                    sh 'terraform init'
			    sh 'terraform apply -auto-approve'
                }
            }
        }
    }
}
