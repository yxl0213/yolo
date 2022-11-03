#Introduction
This document explains how to run YOLOV7, the data sets used, and visualizing the results through the tensorboard.
#Introduction to datasets
There are three kinds of labels for single string tomatoes in greenhouse: red at mature stage, half at semi-mature stage and green at mature stage.

![2](https://user-images.githubusercontent.com/103248636/199666778-7bc52cae-8bfe-4677-9d32-1db06d683a97.jpg)
![3](https://user-images.githubusercontent.com/103248636/199666864-5bb87e40-c50a-4ed2-bcc0-7795529daa90.jpg)
![22](https://user-images.githubusercontent.com/103248636/199666937-3b5e8cfa-bafe-47b3-957c-bae9de868d13.jpg)
![23](https://user-images.githubusercontent.com/103248636/199666941-c59b2cec-7837-4778-b30b-8783c52f7889.jpg)

The directory of the dataset is in the '../mydata5'.

The configuration file for the dataset is in the '../data/mydata5.yaml'.
#Training Environment and results
##Computer configuration
***single GPU-RTX2060***
##Training results
The mAP value is up to 0.85, and there is no fitting phenomenon.
#Training
*python train.py*
```
--workers
0
--device
0
--batch-size
1
--data
data/mydata5.yaml
--img
640
640
--cfg
cfg/training/yolov7.yaml
--weights
runs/train/yolov75/weights/best.pt
--name
yolov7
--hyp
data/hyp.scratch.p5.yaml
--resume
G:/yolov7-main/runs/train/yolov75/weights/epoch_049.pt

```
#Detecting
*python detect.py*
```
--weights
runs/train/yolov75/weights/best.pt
--source
mydata5/images/train
```
The test results are as follows.

