# Introduction
This document explains how to run YOLOV7, the data sets used, and visualizing the results through the tensorboard.
# Introduction to datasets
There are three kinds of labels for single string tomatoes in greenhouse: red at mature stage, half at semi-mature stage and green at mature stage.

![QQ截](https://user-images.githubusercontent.com/103248636/199673159-9b471538-df25-4f24-91d4-833d58a9003a.jpg)

The directory of the dataset is in the '../mydata5'.

The configuration file for the dataset is in the '../data/mydata5.yaml'.
# Training Environment and results
## Computer configuration
***single GPU-RTX2060***
## Training results
A total of 200 rounds of training.The mAP value is up to 0.85, and there is no fitting phenomenon.
# Training
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
# Detecting
*python detect.py*
```
--weights
runs/train/yolov75/weights/best.pt
--source
mydata5/images/train
```
The test results are as follows.

![2](https://user-images.githubusercontent.com/103248636/199673330-54c0f39b-2528-421e-b77f-5c1630f8af84.jpg)
![46](https://user-images.githubusercontent.com/103248636/199673359-717358d0-9936-44d3-a7bc-0e0e62b0003a.jpg)
![11](https://user-images.githubusercontent.com/103248636/199673638-ec303080-94fd-40eb-b7bb-d2a3d916d65f.jpg)
![89](https://user-images.githubusercontent.com/103248636/199673660-e3a7a559-6f7f-4ea2-9cbc-d85cdc13f4af.jpg)

# Variation
***tensorboard***
```
tensorboard --logdir =G:/yolov7-main/runs/train/
```
## Change in learning rate
![0](https://user-images.githubusercontent.com/103248636/199679153-5aba633f-2850-4cf0-8b8c-1188c803202b.jpg)
![1](https://user-images.githubusercontent.com/103248636/199679157-bc480dbc-d076-4fa6-8ec2-4f0e2a78f684.jpg)
![2](https://user-images.githubusercontent.com/103248636/199679159-6c9df312-e33f-4ceb-99d1-729baef8e51a.jpg)
## Change in mAP
![mAP_0 5](https://user-images.githubusercontent.com/103248636/199679266-bec130d7-fdf3-4a01-8b59-657e1081cff8.jpg)
![mAP_0 95](https://user-images.githubusercontent.com/103248636/199679271-f025b623-528e-42c9-931f-cc95c0d3d9d8.jpg)
![precision](https://user-images.githubusercontent.com/103248636/199679276-b2c45622-5551-404b-adbf-eec7697dfc09.jpg)
![recall](https://user-images.githubusercontent.com/103248636/199679279-c5da4c81-2894-4323-8459-391712984c5c.jpg)
## Loss in training data
![box](https://user-images.githubusercontent.com/103248636/199679479-3766f23f-1ffa-4139-99b3-356dc1771639.jpg)
![cls](https://user-images.githubusercontent.com/103248636/199679483-d7bd1e48-0013-4b8c-9988-bd537d2ec22e.jpg)
![obj](https://user-images.githubusercontent.com/103248636/199679485-a0e3fa77-be8f-4dcd-953d-efe8458b38c2.jpg)
## Loss in valid data
![box](https://user-images.githubusercontent.com/103248636/199679646-10aecf37-8820-4f48-ad79-40726869cecc.jpg)
![cls](https://user-images.githubusercontent.com/103248636/199679649-c3659513-4181-4bbc-9295-5ebb0a6c5db8.jpg)
![obj](https://user-images.githubusercontent.com/103248636/199679652-5866a667-bb85-4c5c-be8f-db0edacb38d1.jpg)


