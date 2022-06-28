pipeline {
    agent {
        label 'terraform'
    }
    
     stages {
        stage('AWS Credentials & terraform') {
            steps {
                withCredentials([[
                    $class: 'AmazonWebServicesCredentialsBinding',
	       		credentialsId: '806db635-2ac2-4c77-902e-37fca1baffab',
	                accessKeyVariable: 'AWS_ACCESS_KEY_ID',
	                secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
	                    git branch: 'main', credentialsId: '67b67088-d171-42d3-b4bf-b3a18f5eac79', url: 'https://github.com/Arun2602/vpc.git'
	                    sh 'terraform init'
			    sh 'terraform apply -auto-approve'
                }
            }
        }
    }
}
