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

Then, make sure it is on this list: https://developer.nvidia.com/cuda-gpus



## See where you are

Sometimes you'll get stuck somewhere in the middle, unsure of what actually installed correctly. You don't want to start from the beginning because you don't want to have multiple versions conflicting, but you don't know what you need to do next. That's why I want to start this off with some ways for you to figure out exactly where you are in the process first.



## Instructions with Anaconda

This is my recommendation

Install Anaconda like normal. It's a little annoying on Windows because of how paths work. If you are on windows, don't add it to the path environment in the setup window

What you'll do is open Anaconda3 from the Start menu and ...


`conda create -n tf tensorflow-gpu`






## Visual Studio

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


OK, now let's see if that worked

Open a command prompt and enter `nvcc -V`

> nvcc -V
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2017 NVIDIA Corporation
Built on Fri_Sep__1_21:08:32_Central_Daylight_Time_2017
Cuda compilation tools, release 9.0, V9.0.176

> nvcc -V
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2016 NVIDIA Corporation
Built on Mon_Jan__9_17:32:33_CST_2017
Cuda compilation tools, release 8.0, V8.0.60


Then, run deviceQuery.exe

You should find it somewhere like C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\extras\demo_suite


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

When we say building we mean building from source not installing a wheel file. A wheel is already compiled and 1.4 binaries support CUDA 8 + cuDNN 6. To get CUDA 9 you will need to build from source. I have never done the windows build. Once 1.4 ships the team will switch the nightly builds over to CUDA 9.




However, CUDA 8 does not work with visual studio 2017. See here: https://devtalk.nvidia.com/default/topic/978691/cuda-setup-and-installation/support-for-visual-studio-2017/post/5113817/#5113817



1.4 is CUDA 8 + cuDNN 6 this will not work with CUDA 9 you will have to compile from source
once 1.4 is released we will work to switch the nightly builds to CUDA 9 and then 1.5 will most likely be CUDA 9.



You can download the wheels from here: https://github.com/mind/wheels/releases/tag/tf1.4-gpu-cuda9

It will not be in the nightly as far as linking to CUDA 9. TF 1.4 is next, which will most likely stay CUDA 8 + cuDNN 6 and then 1.5 would move to cuDNN 7 and CUDA 9 if all goes well. 



So I would recommend going with this build:

Visual Studio 2015


## cuDNN

The main page only has the current version, which is 7:

https://developer.nvidia.com/cudnn

The archive stops at version 5: https://developer.nvidia.com/rdp/cudnn-archive

So where to get version 6 and 6.1?


You have to go here to get version 6: https://developer.nvidia.com/rdp/cudnn-download

The tensorFlow documentation says use version 6.1, but I can't find it on their website. But version 6 works

https://www.tensorflow.org/install/install_windows

You can find old versions here: 
https://docs.nvidia.com/deeplearning/cudnn/archives/index.html

## Verifying Visual Studio

Open the nbody Visual Studio solution file for the version of Visual Studio you have installed. 
Click on the build menu, then click Build Solution
It should say:
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========

I did the above but it was after I ran deviceQuery, not sure why I needed to do that


Then get  cuDNN:
the install guide is here:
http://docs.nvidia.com/deeplearning/sdk/cudnn-install/index.html#install-windows

going from here:
C:\Users\HMISYS\Downloads\cudnn-8.0-windows7-x64-v6.0\cuda\lib\x64
to here:
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v8.0

Copy the following files into the CUDA Toolkit directory.
Copy <installpath>\cuda\bin\cudnn64_7.dll to C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v9.0\bin.
Copy <installpath>\cuda\ include\cudnn.h to C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v9.0\include.
Copy <installpath>\cuda\lib\x64\cudnn.lib to C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v9.0\lib\x64.


These can be either system or user variables:
Variable Name: CUDA_PATH 
Variable Value: C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v8.0

now You can install TensorFlow with:

`pip install --upgrade tensorflow-gpu`

 python                                                                                                    
ython 3.6.2 |Anaconda custom (64-bit)| (default, Jul 20 2017, 12:30:02) [MSC v.1900 64 bit (AMD64)] on win3
                                                                                                           
ype "help", "copyright", "credits" or "license" for more information.                                      
>> import tensorflow as tf                                                                                 
>> sess = tf.Session(config=tf.ConfigProto(log_device_placement=True))                                     
017-11-09 16:29:50.126893: I C:\tf_jenkins\home\workspace\rel-win\M\windows-gpu\PY\36\tensorflow\core\platf
rm\cpu_feature_guard.cc:137] Your CPU supports instructions that this TensorFlow binary was not compiled to
use: AVX AVX2                                                                                              
017-11-09 16:29:50.354906: I C:\tf_jenkins\home\workspace\rel-win\M\windows-gpu\PY\36\tensorflow\core\commo
_runtime\gpu\gpu_device.cc:1030] Found device 0 with properties:                                           
ame: GeForce GTX 960 major: 5 minor: 2 memoryClockRate(GHz): 1.291                                         
ciBusID: 0000:01:00.0                                                                                      
otalMemory: 4.00GiB freeMemory: 3.43GiB                                                                    
017-11-09 16:29:50.355906: I C:\tf_jenkins\home\workspace\rel-win\M\windows-gpu\PY\36\tensorflow\core\commo
_runtime\gpu\gpu_device.cc:1120] Creating TensorFlow device (/device:GPU:0) -> (device: 0, name: GeForce GT
 960, pci bus id: 0000:01:00.0, compute capability: 5.2)                                                   
evice mapping:                                                                                             
job:localhost/replica:0/task:0/device:GPU:0 -> device: 0, name: GeForce GTX 960, pci bus id: 0000:01:00.0, 
ompute capability: 5.2                                                                                     
017-11-09 16:29:50.648923: I C:\tf_jenkins\home\workspace\rel-win\M\windows-gpu\PY\36\tensorflow\core\commo
_runtime\direct_session.cc:299] Device mapping:                                                            
job:localhost/replica:0/task:0/device:GPU:0 -> device: 0, name: GeForce GTX 960, pci bus id: 0000:01:00.0, 
ompute capability: 5.2                                                                                     
                                                                                                           

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


