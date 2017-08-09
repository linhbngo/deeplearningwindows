# deeplearningwindows

This is based on http://www.heatonresearch.com/2017/01/01/tensorflow-windows-gpu.html


## Installing
First, you should make sure you have the correct NVidia drivers and tools installed:

http://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/#verify-you-have-cuda-enabled-system

- [CUDA Drivers](https://developer.nvidia.com/cuda-downloads)
- [CUDNN - CUDA for Deep Neural Networks](https://developer.nvidia.com/cudnn)


Need to set up Visual Studio in order to compile and run `deviceQuery`

Installing TensorFlow into Windows Python is a simple pip command. As of the writing of this post, TensorFlow requires Python 2.7, 3.4 or 3.5. In my case I used Anaconda Python 3.5. Read here to see what is currently supported The first thing that I did was create CPU and GPU environment for TensorFlow. This keeps them separate from other non-deep learning Python environments that I have. To create my CPU TensorFlow environment, I used:
1
2
3
4
5
conda create --name tensorflow python=3.5
activate tensorflow
conda install jupyter
conda install scipy
pip install tensorflow
To create my GPU TensorFlow environment, I used:
1
2
3
4
5
conda create --name tensorflow-gpu python=3.5
activate tensorflow-gpu
conda install jupyter
conda install scipy
pip install tensorflow-gpu
Your TensorFlow code will not change using a single GPU. You can simply run the same code by switching environments. TensorFlow will either use the GPU or not, depending on which environment you are in. You can switch between environments with:
1
2
activate tensorflow
activate tensorflow-gpu
Conclusions
If you are doing moderate deep learning networks and data sets on your local computer you should probably be using your GPU. Even if you are using a laptop. NVidia is the GPU of choice for scientific computing. While AMD might be fully capable, support for AMD is much more sparse. 
