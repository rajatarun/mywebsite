node('master'){
	stage('checkout'){
		checkout scm
	}
	stage('depoly to s3'){
		sh('zip build.zip *')
		sh('/home/ec2-user/.local/bin/aws s3 cp build.zip s3://tarunblogwebsite --sse')
	}
}