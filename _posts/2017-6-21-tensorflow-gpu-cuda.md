Installing CUDA


Start with the CPU version: pip install tensorflow


Windows 7, 64-bit

CUDA used to be an acronym for Compute Inified Device Architecture, but now it's no longer an acronym. It's just CUDA.

This tutorial explains how to make your graphics card, or GPU, faster with machine learning.


How to see if it's working


## Hardware Requirements

Before you start, you'll want to make sure that your graphics card is compatible with CUDA. 


First, make sure your graphics card is installed properly and allows CUDA. You can either check your graphics card with the DirectX Diagnostic Tool



If you're on Windows, you can use a tool like [Speccy](https://www.ccleaner.com/speccy).

Then, make sure it is on this list: <https://developer.nvidia.com/cuda-gpus>



#### Verify that there aren't conflicting drivers (Linux only)

verify you have cuda-enabled GPU:

You should see something saying "NVIDIA" when you do:

`lspci | grep -i nvidia`

But you shouldn't see anything from:

`lsmod | grep nouveau` 

If you do, you'll need to remove it


## See where you are

Sometimes you'll get stuck somewhere in the middle, unsure of what actually installed correctly. You don't want to start from the beginning because you don't want to have multiple versions conflicting, but you don't know what you need to do next. That's why I want to start this off with some ways for you to figure out exactly where you are in the process first.


#### Cuda version

`cat /usr/local/cuda/version.txt`

You can see what versions of cuda are avilable:

`conda search cudatoolkit`

You can also find your version by opening a command prompt and enter `nvcc -V`

> nvcc -V
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2017 NVIDIA Corporation
Built on Fri_Sep__1_21:08:32_Central_Daylight_Time_2017
Cuda compilation tools, release 9.0, V9.0.176

```
(tf) julius@julius-MS-7B09:~/git/dTurk$ nvcc --version
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2019 NVIDIA Corporation
Built on Sun_Jul_28_19:07:16_PDT_2019
Cuda compilation tools, release 10.1, V10.1.243
```

#### cuDNN version

It's probably here:

`cat /usr/local/cuda/include/cudnn.h | grep CUDNN_MAJOR -A 2`

But if you're not sure you can check here:
`cat $(whereis cudnn.h) | grep CUDNN_MAJOR -A 2`

`cat $(whereis cuda)/include/cudnn.h | grep CUDNN_MAJOR -A 2`

###### Windows

If you're on Windows you should be able to find them here:
`C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\include`

You can also type this: `where cudnn*`

## Compatibility

This is a big deal in all this.

#### Cuda and Tensorflow and cuDNN

Tensorflow maintains [this chart](https://www.tensorflow.org/install/source#gpu) with the latest compatibility information.

## Instructions with Anaconda

This is my recommendation

Install Anaconda like normal. It's a little annoying on Windows because of how paths work. If you are on Windows, don't add it to the path environment in the setup window

What you'll do is open Anaconda3 from the Start menu and ...

Although tensorflow-gpu and tensorflow is a distinction of version <= 1.15, the distinction matters quite a lot here. If you do `conda create -n tf tensorflow` it will not create a GPU version, even though it installs a 2.X version of Tensorflow. You'll need to use `conda create -n tf tensorflow-gpu` to get the GPU version.


## Visual Studio (old)

On Windows, you may need Visual Studio for this. You will use it to compile CUDA projects. Check here to make sure your version of Visual Studio can work with CUDA: http://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/index.html

Look at Table 2

Note that this is for the most recent version of CUDA, which is CUDA 9.0 at the moment. CUDA 9.0 works with many different versions of VS, but not with Tensorflow

I'm using Visual Studio Community 2017, which I [downloaded for free](https://www.visualstudio.com/downloads/). 

You can also [download older versions here](https://www.visualstudio.com/vs/older-downloads/). You need to join a Microsoft Dev Essentials program, but joining is free. You'll need Visual Studio Community 2015 with Update 3

## Tensorflow and CUDA compatibility

Make sure you check what version of CUDA to install. The latest version will not necessarily be supported by TensorFlow.

Check here for the version: https://www.tensorflow.org/install/install_windows



To check your driver version you can go to GEForce Experience and click on "Drivers"
Install the most recent NVIDIA Driver: http://www.nvidia.com/Download/index.aspx?lang=en-us


Then install the CUDA Toolkit: https://developer.nvidia.com/cuda-downloads
If you want an older version, you can go here: https://developer.nvidia.com/cuda-10.1-download-archive-base
After you input your operation system information, you have the option of downloading either the network or local installer. Either will work. " The Network Installer allows you to download only the files you need. The Local Installer is a stand-alone installer with a large initial download."

Here's an example extraction path: C:\Users\Julius\AppData\Local\Temp\CUDA


OK, now let's see if that worked by running `nvcc --version`



Then, run deviceQuery.exe

You should find it somewhere like `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\extras\demo_suite`


Go to a command prompt and run it by typing "deviceQuery.exe". Note that you cannot go to the folder and double click on it or it will open a command prompt, run, and close too quickly for you to see the results.


Answering this question:


Using these sites:

http://blog.nitishmutha.com/tensorflow/2017/01/22/TensorFlow-with-gpu-for-windows.html


https://www.tensorflow.org/install/install_windows - can I update this documentation? Is it open source?



To check your version:

Open a python console
``` python
import tensorflow as tf
tf.__version__
```
Then to upgrade it, `pip install tensorflow --upgrade`



All those chomping at the bit, just build #master from source. It's not too hard (just time consuming), you get the latest CUDA/cuDNN, and additional optimizations over a pip/whl install (eg, see the CPU optimizations in this tut). Plus next time CUDA/cuDNN upgrade, you can build again w/o having to wait.

When we say building we mean building from source not installing a wheel file. A wheel is already compiled and 1.4 binaries support CUDA 8 + cuDNN 6. To get CUDA 9 you will need to build from source. I have never done the Windows build. Once 1.4 ships the team will switch the nightly builds over to CUDA 9.




However, CUDA 8 does not work with visual studio 2017. See here: https://devtalk.nvidia.com/default/topic/978691/cuda-setup-and-installation/support-for-visual-studio-2017/post/5113817/#5113817



1.4 is CUDA 8 + cuDNN 6 this will not work with CUDA 9 you will have to compile from source
once 1.4 is released we will work to switch the nightly builds to CUDA 9 and then 1.5 will most likely be CUDA 9.



You can download the wheels from here: https://github.com/mind/wheels/releases/tag/tf1.4-gpu-cuda9

It will not be in the nightly as far as linking to CUDA 9. TF 1.4 is next, which will most likely stay CUDA 8 + cuDNN 6 and then 1.5 would move to cuDNN 7 and CUDA 9 if all goes well. 



So I would recommend going with this build:

Visual Studio 2015

## CUDA on Ubuntu

You should be able to install on a debian-based Linux with `sudo apt install nvidia-cuda-toolkit`

Now you should be able to see it when you check your CUDA version (`nvcc --version`)

## cuDNN

The main page only has the current version, which is 7:

You can find the [latest version of cuDNN here](https://developer.nvidia.com/rdp/cudnn-download). However, you'll probably need a version from the [cuDNN archive](https://developer.nvidia.com/rdp/cudnn-archive).

You can also find the [release notes on old versions of cuDNN](https://docs.nvidia.com/deeplearning/cudnn/archives/index.html).

#### Windows

The install guide is here:
[
Then get  cuDNN:
the install guide is here:
[http://docs.nvidia.com/deeplearning/sdk/cudnn-install/index.html#install-windows](http://docs.nvidia.com/deeplearning/sdk/cudnn-install/index.html#install-windows)

On Windows the procedure is similar. Download and unzip the files. 

For me, they download into a folder like C:\Users\Julius\Downloads\cudnn-10.1-windows10-x64-v7.6.5.32




Then you have to copy files:

Copy the following files into the CUDA Toolkit directory.

```

going from here:
C:\Users\HMISYS\Downloads\cudnn-8.0-windows7-x64-v6.0\cuda\lib\x64
to here:
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v8.0

Copy the following files into the CUDA Toolkit directory.
Copy <installpath>\cuda\bin\cudnn64_7.dll to C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v9.0\bin.
Copy <installpath>\cuda\ include\cudnn.h to C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v9.0\include.
Copy <installpath>\cuda\lib\x64\cudnn.lib to C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v9.0\lib\x64.
```

Make sure you get the version right. You can cd to `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA` and the use `dir` to see what versions you have (it should match what you previously saw).

After extracting the files, here's my install path:
C:\Users\Julius\Downloads\cudnn-10.1-windows10-x64-v7.6.5.32

For these to work you'll probably need to run as administrator


Then, from your install path, you'll want to:

`copy cuda\bin\cudnn*.dll "C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\bin"`
`copy cuda\include\cudnn*.h "C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\include"`
`copy cuda\lib\x64\cudnn*.lib "C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\lib\x64"`

Make sure your destination is right too:
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\bin



#### Installing

Once you've downloaded the correct version, it will probably be in a Download folder, somewhere like `/home/julius/Downloads`

You'll need to extract it with something like this:
`tar -xzvf cudnn-10.1-linux-x64-v7.6.5.32.tgz`

Then you'll need to copy the files like so:
``` bash
$ sudo cp cuda/include/cudnn*.h /usr/local/cuda/include
$ sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
```
Then change the permissions like so:
``` bash
$ sudo chmod a+r /usr/local/cuda/include/cudnn*.h /usr/local/cuda/lib64/libcudnn*
```
                                                                               
                                                                                                           
## Paths

On Unix machines, you'll need to add these to your .bashrc:
```
export CUDA_HOME=/usr/local/cuda
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda/lib64:/usr/local/cuda/extras/CUPTI/lib64
export INCLUDE=/usr/local/cuda/include
```

## Test if Tensorflow is working on the GPU

You can see all your physical devices like so:
``` python
import tensorflow as tf
tf.config.experimental.list_physical_devices()
```
and you can limit them to the GPU:
``` python
tf.config.experimental.list_physical_devices('GPU')
```
``` python
print("Num GPUs Available: ", len(tf.config.experimental.list_physical_devices('GPU')))
```



## gcc

Make sure you have gcc:
gcc --version

## You can also look at CUDNN with PyTorch

`print(torch.__config__.show())`

![png](assets/torch.png)
