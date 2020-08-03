default: latest intel nvidia pal

latest: intel
	docker tag diegoferigo/devenv:intel diegoferigo/devenv:latest

intel:
	docker build --rm \
		--build-arg from=ubuntu:bionic \
		--build-arg VCS_REF=`git rev-parse --short HEAD` \
		--build-arg BUILD_DATE=`date -u +"%Y-%m-%dT%H:%M:%SZ"` \
		--tag diegoferigo/devenv:intel \
		.

nvidia:
	docker build --rm \
		--build-arg from=nvidia/cuda:10.1-cudnn7-runtime-ubuntu18.04 \
		--build-arg VCS_REF=`git rev-parse --short HEAD` \
		--build-arg BUILD_DATE=`date -u +"%Y-%m-%dT%H:%M:%SZ"` \
		--tag diegoferigo/devenv:nvidia \
		.

pal:
	docker build --rm \
		--build-arg from=registry.gitlab.com/pal-robotics/waterloo-university-reem-c/dockers/reemc-7-erbium \
		--build-arg VCS_REF=`git rev-parse --short HEAD` \
		--build-arg BUILD_DATE=`date -u +"%Y-%m-%dT%H:%M:%SZ"` \
		--tag fjandrad/devenv:pal \
		.

# TODO
# update_nvidia_opengl:

push_latest:
	docker push diegoferigo/devenv:latest
	
push_intel:
	docker push diegoferigo/devenv:intel
	
push_nvidia:
	docker push diegoferigo/devenv:nvidia
