
aliyun_username := $(shell echo $$ALIYUN_USERNAME)
aliyun_password := $(shell echo $$ALIYUN_PASSWORD)

aliyun_login:
	docker login --username=$(aliyun_username) registry.cn-hangzhou.aliyuncs.com --password=$(aliyun_password)

aliyun_build: aliyun_login
	docker build . -t registry.cn-hangzhou.aliyuncs.com/pony-ma/browerless-chrome --platform=linux/amd64

aliyun_push: aliyun_build
	docker push registry.cn-hangzhou.aliyuncs.com/pony-ma/browerless-chrome


aws_login:
	aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/u1w0u1f8

aws_build: aws_login
	docker build . -t public.ecr.aws/u1w0u1f8/browerless-chrome:latest --platform=linux/amd64

aws_push: aws_build
	docker push public.ecr.aws/u1w0u1f8/browerless-chrome:latest
