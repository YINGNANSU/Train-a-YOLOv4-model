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

Ubuntu Linux Python5 + Qt5
         
     git clone https://github.com/tzutalin/labelImg.git
     sudo apt-get install pyqt5-dev-tools
     sudo pip3 install -r requirements/requirements-linux-python3.txt
     make qt5py3
     cd labelImg

     python3 labelImg.py
     python3 labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]
    
    
 * JPEGImages -- Store all [.jpg] imgages
 * Annotations -- Store all labeled [.xml] file
 * labels -- Transfer all labeled [.xml] file to [.txt] file
   
       python3 ./tools/voc_label.py (change and check your file paths)
       
##  Make path[.txt] file

### First you have to devide your dataset into train dataset and validation dataset.

       python3 ./tools/img2train.py [img path]
    
 
 * train.txt -- Store all train_img name without .jpg
 * val.txt -- Store all val_img name without .jpg

### Run voc_label.py can get below file

 * object_train.txt:Store all train_img paths
 * object_val.txt:Store all val_img paths

 ## Make [.names] [.data] and [.cfg] file
 
