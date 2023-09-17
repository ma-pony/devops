
aliyun_username := $(shell echo $$ALIYUN_USERNAME)
aliyun_password := $(shell echo $$ALIYUN_PASSWORD)

login:
	docker login --username=$(aliyun_username) registry.cn-hangzhou.aliyuncs.com --password=$(aliyun_password)

build: login
	docker build . -t registry.cn-hangzhou.aliyuncs.com/pony-ma/python-playwright --platform=linux/amd64

push: build
	docker push registry.cn-hangzhou.aliyuncs.com/pony-ma/python-playwright
