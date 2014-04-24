# Detect bounding boxes of objects in images irrespective of class/category.

This is a fork of the BING Objectness code from www.mmcheng.net/bing for Unix.
It should also compile on Windows as intended by the original author (not tested).

It implements the techniques described in the following paper:
BING: Binarized Normed Gradients for Objectness Estimation at 300fps. 
Ming-Ming Cheng, Ziming Zhang, Wen-Yan Lin, Philip Torr.
IEEE CVPR, 2014. [pdf](http://mmcheng.net/mftp/Papers/ObjectnessBING.pdf)

These are the results that I obtained using the fast detection variant 
1:0.25,0.304  10:0.481,0.449  100:0.794,0.607 1000:0.958,0.669  
2000:0.969,0.673  3000:0.969,0.673  4000:0.969,0.673  5000:0.969,0.673

## Prerequisites
Download the [VOC 2007 train data](http://pascallin.ecs.soton.ac.uk/challenges/VOC/voc2007/VOCtrainval_06-Nov-2007.tar
) and put them in the VOC2007 directory. 
Do not copy the ImageSets directory from the VOC dataset, retain the version supplied with this code.

Download the [VOC2007 test data] (http://pascallin.ecs.soton.ac.uk/challenges/VOC/voc2007/VOCtest_06-Nov-2007.tar) 
Move all images from <test>/JPEGImages folder to the earlier extracted VOC2007/JPEGImages folder.

Unzip the Annotations.zip file in the VOC2007 folder. 
-Or-
Download an OpenCV readable version of [VOC 2007 annotations](http://mmcheng.net/mftp/Data/VOC2007_AnnotationsOpenCV_Readable.7z). 


## Building from source
Modify the CMakeLists.txt file as needed. For example, to set OpenCV directory.
```
mkdir build
cd build
cmake ..
make
```