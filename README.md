图像修复（Image inpainting）是一个已经被广泛研究的计算机视觉问题，即恢复图像中缺失的部分。斯坦福大学CS230课程的Mark Sabini等人提出“Image outpainting”，比图像修复更进一步，能从一个图像片段“推断”出外延的部分，补全成整个画面。这篇论文获得了CS230期末poster的第一名，效果非常惊艳。



代码和论文地址：

https://github.com/bendangnuksung/Image-OutPainting

https://cs230.stanford.edu/projects_spring_2018/posters/8265861.pdf

# Keras implementation of Image OutPainting

This is an implementation of [Painting Outside the Box: Image Outpainting](https://cs230.stanford.edu/projects_spring_2018/posters/8265861.pdf) paper from Standford University. 
Some changes have been made to work with 256*256 image:
  - Added Identity loss i.e from generated image to the original image
  - Removed patches from training data. (training pipeline)
  - Replaced masking with cropping. (training pipeline)
  - Added convolution layers.

## Results
The model was train with [beach data](http://cvcl.mit.edu/scenedatabase/coast.zip)  for 200 epochs.
![Demo](https://i.imgur.com/lmhhIqv.png)

#### Recursive painting
![Demo](https://i.imgur.com/RCp4Wzc.png)

## Tested with
  - python 3.5
  - keras==2.1.5
  - keras-contrib==2.0.8
  - tensorflow==1.5.0
  - opencv-python==3.4.0.12
  - Pillow==5.0.0
  - CUDA Version 9.0.176

## Get Started
1. Prepare Data:
      ```sh
      # Downloads the beach data and converts to numpy batch data
      # saves the Numpy batch data to 'data/prepared_data/'
      sh prepare_data.sh
      ```
2. Build Model
    * To build Model from scratch you can directly run 'outpaint.ipynb'
  <br/>OR<br/>
    * You can [Download](https://drive.google.com/file/d/1548iAtsNf3wLSc1i5zYy-HX8_TW95wi_/view?usp=sharing) my trained model and move it to 'checkpoint/' and run it.

## References
* [Painting Outside the Box: Image Outpainting](https://cs230.stanford.edu/projects_spring_2018/posters/8265861.pdf)
