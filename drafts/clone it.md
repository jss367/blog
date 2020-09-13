clone it

cd docker/

docker build --build-arg USER_ID=$UID -t detectron2:v0 .



docker run --gpus all -it \
	--shm-size=8gb --env="DISPLAY" --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" \
	--name=detectron2 detectron2:v0




note: I use cmder on Windows 10 Pro - Pro is a must


E: Failed to fetch http://archive.ubuntu.com/ubuntu/pool/main/a/at-spi2-core/at-spi2-core_2.28.0-1_amd64.deb  Undetermined Error [IP: 91.189.88.152 80]
E: Unable to fetch some archives, maybe run apt-get update or try with --fix-missing?
The command '/bin/sh -c apt-get update && apt-get install -y    python3-opencv ca-certificates python3-dev git wget sudo        cmake ninja-build protobuf-compiler libprotobuf-dev &&   rm -rf /var/lib/apt/lists/*' returned a non-zero code: 100




docker run --gpus all -it \
	--shm-size=8gb --env="DISPLAY" --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" \
	--name=detectron2 detectron2:v0

invalid format

docker run --gpus all -it --shm-size=8gb --env="DISPLAY" --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" --name=detectron2 detectron2:v0



λ docker run --gpus all -it --shm-size=8gb --env="DISPLAY" --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" --name=detectron2 detectron2:v0
Unable to find image 'detectron2:v0' locally
docker: Error response from daemon: pull access denied for detectron2, repository does not exist or may require 'docker login': denied: requested access to the resource is denied.
See 'docker run --help'.


