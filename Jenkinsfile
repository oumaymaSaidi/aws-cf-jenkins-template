pipeline {
	agent any
	stages {
		stage('Clone Repo') {
			steps {
		  sh '''
		  export AWS_DEFAULT_REGION=eu-west-1
		  if aws cloudformation describe-stacks  --query 'Stacks[].StackName' | grep JenkinsStack ; then
		  aws cloudformation update-stack --stack-name JenkinsStack --template-body file://S3Bucket.json --region 'eu-west-1'
		  else
		  aws cloudformation create-stack --stack-name JenkinsStack --template-body file://S3Bucket.json --region 'eu-west-1'
          fi
		  '''
		  }
		}
	}
}