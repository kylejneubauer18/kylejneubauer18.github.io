---
layout: project
type: project
image: images/################################################
title: CRB Image Classification
permalink: projects/redlabcrb
# All dates must be YYYY-MM-DD format!
date: 2021-05-10
labels:
  - Machine Learning
  - Deep Learning
  - Image Classification
  - Environment Friendly
  - Transfer Learning
  - Python
  - CNN
summary: To build an algorithm that analyzes visual imagry of coconut rhinocerous beetles and other native insects of hawaii and categorizes them to be then identified among 3000 traps across Oahu to greatly improve trap checking efficiency as well as exponentially raising the catch rate of given areas.
---
<div class="ui centered high rounded images">
  <img class="ui centered image" src="../images/cnn.PNG">
</div>

<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The objective of this project is to build a machine learning algorithm that works along side OpenMV to create computer vision to successfully detect Coconut Rhinoceros Beetles. Convolutional neural networks (CNN), a deep learning algorithm best used for image classification, was used detect and identify multiple native hawaiian insects and the non-native coconut rhinoceros beetles. This project is the first step in helping the environment and coconut trees across hawaii as it could be further improved for other islands and countries. With the assistance of monitoring multiple traps, it could provide invaluable data and information by tracking entire colonies in real time. With machine learning, we could makes protecting the environment much easier and affordable for everyone!
</p>

<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The project consisted of two groups, the arduino coding team, and the machine learning team. The arduino team focused on researching what hardware to use, importing modules, connecting to wifi/LTE, connecting and recieving data from url, managing device power, device sleep time, and more. OpenMV was decided on as the optimal choice as it supports machine learning libraries, is compact and small enough to fit into traps, supports a wifi shield, and is low power (less than 200mA) so that it can be powered by solar energy. As for the machine learning team, Tensorflow was utilized as it is a free open source library for machine learning. Tensorflow was the optimal choice becase it can be coded in python which has a lot of resources and code to learn from and it can be easily exported to embedded systems like OpenMV. The machine learning team created a convolutional neural network to identify coconut rhinoceros beetles and with the help of transfer learning, utilized the pre-trained MobileNet model. By using transfer learning the machine learning team could obtain a higher accuracy, a faster training time, and was overall less computationally intensive. The machine learning team trained on cats and dogs initially, but switched to coconut rhinoceros beetles and hawaiian insects once they were able to obtain more images. After obtaining the desired accuracy, the machine learning team used quantization to load it onto the mobile device.
</p>

<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;I was part of the coding team and my task involved researching current types of algorithms that may improve testing accuracies and building from the ground up with corresponding kernals. Some types of machine learning algorithms built and analyzed involved convolutional neural netowkrs (CNN), linear support vector machines (Linear SVM), and non-linear support vector machines (non-linear SVM). Every other day over the course of two weeks we would meet online to discuss current progress and work towards optimizing our parameters to improve accuracy further. I was able to get three working algorithms with all accuracies above 90% and successfully completed my tasks. The Future plans for this project is to enchance the algorithm and teach the algorithm to identify new characters such as the alphabet.
</p>

<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Working on the coding part of this Machine Learning project really helped me grow and expand my knowledge on what exactly machine learning can do. I was able to pick up learning to code in Tensorflow and Python very quickly and with the help of kernals I could accomplish my goals much faster than I expected. I also learned how to optimize my machine learning algorithms and adjust their hyper parameters to boost the accuracy of the models.
</p>

If you would like to view our project's final paper you can view it [here](https://github.com/kylejneubauer18/kylejneubauer18.github.io/blob/e80277c76e898d16b2e9b0d2234996df5a824d13/EE%20445%20Final%20Paper.pdf).
