
NAME := my-nvidia-cuda-1

all:

build:
	docker build . -t my-nvidia-cuda

up:
	docker run --name ${NAME} -v ~/share:/root/share -p 2222:2222 --gpus all -it --rm -d my-nvidia-cuda

down:
	docker stop ${NAME}

sh:
	docker exec -it ${NAME} bash

