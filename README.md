# ai-dqn
Nvidia ai-dqn experiments

docker pull nvidia/cuda:8.0-cudnn5-runtime-ubuntu16.04

nvidia-docker run -it --name ai-dqn -v /tmp/.X11-unix:/tmp/.X11-unix -v /docker-mounts:/docker-mounts -e DISPLAY=unix$DISPLAY --device /dev/dri --device /dev/snd nvidia/cuda:8.0-cudnn5-runtime-ubuntu16.04 bash

 - apt-get update
 - apt-get install vim
 - apt-get install git
 - apt-get upgrade

 - apt-get install python-pip python-dev
 - apt-get install libcupti-dev
 
 - pip install --upgrade pip
 - pip install tensorflow-gpu 
 
 - cd
 - mkdir experiments
 - cd experiments 
 - git clone https://github.com/devsisters/DQN-tensorflow.git
 
 - pip install tqdm gym[all]
 - apt-get install xvfb libav-tools xorg-dev libsdl2-dev swig cmake
 - pip install tqdm gym[all] 
 
 - python main.py --env_name=Breakout-v0 --is_train=True --display=True
 - pip install atari-py==0.0.21
 - python main.py --env_name=Breakout-v0 --is_train=True --display=True

nvidia-docker commit ai-dqn stefanutti/cuda:8.0-cudnn5-runtime-ubuntu16.04-tf-dqn-1.2

nvidia-docker rm ai-dqn

nvidia-docker run -it --name ai-dqn -v /tmp/.X11-unix:/tmp/.X11-unix -v /docker-mounts:/docker-mounts -e DISPLAY=unix$DISPLAY --device /dev/dri --device /dev/snd stefanutti/cuda:8.0-cudnn5-runtime-ubuntu16.04-tf-dqn-1.2 bash

nvidia-docker start ai-dqn

nvidia-docker exec -it ai-dqn bash

