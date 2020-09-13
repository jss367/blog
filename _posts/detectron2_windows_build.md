
windows


docker build --build-arg USER_ID=$UID -t detectron2:v0 .


Step 6/22 : RUN useradd -m --no-log-init --system  --uid ${USER_ID} appuser -g sudo
 ---> Running in 666fd19e6f78
useradd: invalid user ID '$UID'
The command '/bin/sh -c useradd -m --no-log-init --system  --uid ${USER_ID} appuser -g sudo' returned a non-zero code: 3


detecrton2 wsl



docker build --build-arg USER_ID=$UID -t detectron2:v0 .








to access wsl, can just type wsl from terminal... i was opening up the ubuntu tab

then just `code .`

It will download automatically





wsl -l -v - tells your your version info
Can't run it in WSL, must run it from command line in windows






put code in the linux part



docker run -v <host-path>:<container-path>


Linux containers only receive file change events (“inotify events”) if the original files are stored in the Linux filesystem.
Performance is much higher when files are bind-mounted from the Linux filesystem, rather than remoted from the Windows host. Therefore avoid docker run -v /mnt/c/users:/users (where /mnt/c is mounted from Windows).


From the terminal in VSCode:
python demo.py --config-file ../configs/COCO-InstanceSegmentation/mask_rcnn_R_50_FPN_3x.yaml \
  --input input1.jpg input2.jpg \
  --opts MODEL.WEIGHTS detectron2://COCO-InstanceSegmentation/mask_rcnn_R_50_FPN_3x/137849600/model_final_f10217.pkl


- but you get a problem that says you don't have python. You need to be in a container

cd to detectron2/docker
docker build --build-arg USER_ID=$UID -t detectron2:v0 .


If you docker run --gpus all -it \
	--shm-size=8gb --env="DISPLAY" --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" \
	--name=detectron2 detectron2:v0

You'll get docker: Error response from daemon: could not select device driver "" with capabilities: [[gpu]].



before you

nvidia-container-toolkit




Must install an NVIDIA driver first. Check with `nvidia-smi` and `nvcc--version`

also docker version must be greater than 19.03 `docker --version`

audo apt-get update
sudo apt install nvidia-340

NVIDIA-SMI has failed because it couldn't communicate with the NVIDIA driver. Make sure that the latest NVIDIA driver is installed and running.

sudo apt install nvidia-utils-390


sudo apt install nvidia-cuda-toolkit




nvcc --version
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2017 NVIDIA Corporation
Built on Fri_Nov__3_21:07:56_CDT_2017
Cuda compilation tools, release 9.1, V9.1.85



Next: try to disable secure boot.
https://askubuntu.com/questions/927199/nvidia-smi-has-failed-because-it-couldnt-communicate-with-the-nvidia-driver-ma


