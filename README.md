# How to train YOLOv4 model with own dataset

## Environment
Ubuntu 18.04
CUDA 10.0
cuDNN 7.6.0
Python 3.6
OpenCV 4.2.0

##Download the source code

git clone https://github.com/AlexeyAB/darknet.git
cd darknet

vim Makefile


    GPU=1 to build with CUDA to accelerate by using GPU (CUDA should be in /usr/local/cuda)
    CUDNN=1 to build with cuDNN v5-v7 to accelerate training by using GPU (cuDNN should be in /usr/local/cudnn)
    CUDNN_HALF=1 to build for Tensor Cores (on Titan V / Tesla V100 / DGX-2 and later) speedup Detection 3x, Training 2x
    OPENCV=1 to build with OpenCV 4.x/3.x/2.4.x - allows to detect on video files and video streams from network cameras or web-cams
    DEBUG=1 to bould debug version of Yolo
    OPENMP=1 to build with OpenMP support to accelerate Yolo by using multi-core CPU
    LIBSO=1 to build a library darknet.so and binary runable file uselib that uses this library. Or you can try to run so LD_LIBRARY_PATH=./:$LD_LIBRARY_PATH ./uselib test.mp4 How to use this SO-library from your own code - you can look at C++ example: https://github.com/AlexeyAB/darknet/blob/master/src/yolo_console_dll.cpp or use in such a way: LD_LIBRARY_PATH=./:$LD_LIBRARY_PATH ./uselib data/coco.names cfg/yolov4.cfg yolov4.weights test.mp4
    ZED_CAMERA=1 to build a library with ZED-3D-camera support (should be ZED SDK installed), then run LD_LIBRARY_PATH=./:$LD_LIBRARY_PATH ./uselib data/coco.names cfg/yolov4.cfg yolov4.weights zed_camera

