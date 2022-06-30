pipeline {
    agent {
        label 'terraform'
    }
    
     stages {
        stage('AWS Credentials & terraform') {
            steps {
                withCredentials([[
                    $class: 'AmazonWebServicesCredentialsBinding',
	       		credentialsId: 'aws-access-secret-credentials',
	                accessKeyVariable: 'AWS_ACCESS_KEY_ID',
	                secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
	                    sh 'terraform init'
			    sh 'terraform apply -auto-approve'
                }
            }
        }
    }
}
