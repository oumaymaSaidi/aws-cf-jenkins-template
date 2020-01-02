pipeline {
	agent any
	stages {
		stage('Clone Repo') {
			steps {
		  sh "export AWS_DEFAULT_REGION=eu-west-1"
		  sh "aws cloudformation create-stack --stack-name JenkinsStack --template-body file://S3bucket.json --region 'eu-west-1'"
		  
		  }
		}
	}
}