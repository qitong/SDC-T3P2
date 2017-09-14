# SDC-T3P2
Udacity Semantic Segmentation ADL

## Model Architecture
---  
I use FCN (Fully Convolutional Network) for this semantic segmentation project, which mainly reimplemts the Fully Convolutional Networks for Semantic Segmentation paper of Jonathan Long, Evan Shelhamer, Trevor Darrell. The encoder used pretrained VGG-16, then the decoder connect the last layer before full connected to 1x1 conv layer to pertain spatial informations, then use upsampling (deconv) layer to project classification info onto the original image; and to include more detailed boundary info, it applies skip layer to add the layer of same size in encoder to the upsampled result of deconv layer.   
The hyperparameters are choosed accordingly, which depends on the number of classifaction classes, the upsampling stride (2,2,8) for each layer and the size of corresponding encoder layer feature map.  

Though I have finished the project (I think …), I have to ask several questions:
1. What is function of the full connected part of VGG16， if it is not used, why not cut it and save the memory?
2. Why is layer 3 4 and 7, I think 7 is definitely useful but why prefer 3 and 4 over other pooled layers?


## Result
---
The model is trained on my Ubuntu with NVidia 1080Ti.   
The segmentation result resides in run/ folder.   
(The FCN network result is coarse at boundary and I'm working on SegNet on my own to try to solve the problem.)  
The following images are from my result:


![](https://github.com/qitong/SDC-T3P2/raw/master/runs/1505363622.1494074/umm_000065.png)  
![](https://github.com/qitong/SDC-T3P2/raw/master/runs/1505363622.1494074/um_000060.png) 
![](https://github.com/qitong/SDC-T3P2/raw/master/runs/1505363622.1494074/uu_000089.png) 

