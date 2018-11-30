# Computer_solutions  
## You can find various solutions 
##  GPU configuration for deep learning model(tesorflow-gpu) in ubuntu 18.04     
you need to check your driver version.   
sudo ubuntu-driver devices

 You can check your ubuntu additional software and drivers and install drivers 
 Install CUDA Toolkit 10.0 from https://developer.nvidia.com/cuda-toolkit
 
 Install CUDNN 9.0 library   
 https://developer.nvidia.com/cudnn   
 you need to signup here (it's free). Once downloaded, unpack the archive and move it the contents into the directory where you install CUDA 10.0  
 ## Unpack the archive
tar -zxvf cudnn-10.0-linux-x64-v7.tgz

## Move the unpacked contents to your CUDA directory
sudo cp -P cuda/lib64/libcudnn* /usr/local/cuda-10.0/lib64/
sudo cp  cuda/include/cudnn.h /usr/local/cuda-10.0/include/

## Give read access to all users
sudo chmod a+r /usr/local/cuda-10.0/include/cudnn.h /usr/local/cuda/lib64/libcudnn*  
## Install libcupti  
sudo apt-get install libcupti-dev
## Do the CUDA post-install actions
export PATH=/usr/local/cuda-10.0/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=/usr/local/cuda/lib64:${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}  
## Install Tensorflow GPU  
pip install --upgrade tensorflow-gpu
