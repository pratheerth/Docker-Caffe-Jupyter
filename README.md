# Docker-Caffe-Jupyter
### Install docker<br>
https://www.docker.com/

### Install Nvidia docker<br>

If you use GPU, please install Nvidia docker<br>
https://github.com/NVIDIA/nvidia-docker<br>
### Download caffe image<br>
##### CPU version<br>
```docker run -ti bvlc/caffe:cpu caffe --version>```<br>
##### GPU version<br>
```nvidia-docker run -ti bvlc/caffe:gpu caffe --version```<br>
After above operations,you should see these images:<br>
```docker images```
```
  REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
  nvidia/cuda         latest              1b0262301072        4 days ago          1.94GB
  bvlc/caffe          gpu                 ba28bcb1294c        8 weeks ago         3.38GB
```
### Enter container
```
docker run -p 5555:8888 -i -t imagename /bin/bash # assign a port like 5555 or 7777
```
### Install jupyter notebook
```python
pip install jupyter notebook
```
### Configure
```
wget https://raw.githubusercontent.com/waszy110/Docker-Caffe-Jupyter/master/jupyter_notebook_config.py -P /root/.jupyter/
```
### Run jupyter notebook
```
jupyter notebook --allow-root
```
### Open jupyter notebook<br>
http://localhost:5555/ #password is 000 <br>
### Build a new image include caffe and jupyter
##### check running container id 
```docker ps ```
##### Build new image
```
docker commit containerid newimagename
```
##### Run new image
```
docker run -p 5555:8888 -i -t newimagename /bin/bash
```
### Some simple operations

##### Download image
```
docker pull imagename
```
##### Run a container
```
docker run -it imagename
```
##### Stop container
```
docker stop containerid 
```
##### Remove container 
```
docker rm containerid
```
##### Remove image
```
docker rmi imageid
```
##### Check image id
```
docker images
```

