# How to train YOLOv4 model on own dataset

## Environment
 * Ubuntu 18.04
 * CUDA 10.0
 * cuDNN 7.6.0
 * Python 3.6
 * OpenCV 4.2.0

## Download the source code

    git clone https://github.com/AlexeyAB/darknet.git
    cd darknet

    vim Makefile

    GPU=1
    CUDNN=1 
    CUDNN_HALF=1 
    OPENCV=1 
    DEBUG=1 
    OPENMP=1 
    LIBSO=1 
    ZED_CAMERA=1 
    
    make
    
## Download pre-trained weights file
[yolov4.conv.137](https://drive.google.com/file/d/1JKF-bdIklxOOVy-2Cr5qdvjgGpmGfcbp/view)
    
## Image labeling
LabelImg is a graphical image annotation tool - [labelImg](https://github.com/tzutalin/labelImg)

