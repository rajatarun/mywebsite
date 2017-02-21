node('master'){
	stage('checkout'){
		checkout scm
	}
	stage('depoly to s3'){
		sh('zip build.zip *')
		sh('pip install --upgrade --user awscli')
		sh('aws s3 cp build.zip s3://tarunblogwebsite --sse')
	}
}
