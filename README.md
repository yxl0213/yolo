# Introduction
This document explains how to train the mindspore-yolov7 model and how to display test results in a validation set.

The entire package needs to be placed directly on the G disk

# Introduction to datasets
There are three kinds of labels for single string tomatoes in greenhouse: red at mature stage, half at semi-mature stage and green at mature stage.

![QQ截](https://user-images.githubusercontent.com/103248636/199673159-9b471538-df25-4f24-91d4-833d58a9003a.jpg)

The directory of the dataset is in the './mydata5'.

The configuration file for the dataset is in the './config/data/mydata5.yaml'.
# Training environment and results
## Computer configuration
***mindspore1.9.0 CPU Windows-x64 Python3.8 Conda***
## Training results
A total of 44 rounds of training.Loss drops to 0.03. 

## How to train
 
Run *train.py* directly.

The final model configuration is ‘***G:/yolov7_mindspore-main/runs/train/exp10/weights/EMA_yolov7_44.ckpt***’.

## How to test

Run *test1.py* directly.

The results are as follow.
![449bce1d6049cf539de62ac0521d4d2](https://user-images.githubusercontent.com/103248636/205432935-8f445623-de9c-489d-8344-b91166a35dc7.png)

