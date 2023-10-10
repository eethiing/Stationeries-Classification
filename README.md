# Stationeries-Classification-using-CNN

## Description 
----------------------------------------------------------------------------------------------------------------------
This project aims to classify the stationeries based on the images collected. There are a total of 5000 images for 5 classes (eraser[0], notebook[1], pen[2], scissors[3], tape[4]). The data was collected by capturing the pictures manually and web scraping. Convolutional Neural Network (CNN) is used in this project to classify the data. 

## Proposed Architecture
----------------------------------------------------------------------------------------------------------------------
The proposed architecture uses 3 convolutional layers, 3 pooling layers, 1 flatten layer and 3 fully-connected layers. For the convolutional layers, a kernel size of 3x3 is utilised and for the pooling layers, the pooling size is set to 2x2. The flatten layer is used to convert the feature maps into 1D vectors. As for the fully connected layers, the first two layers will be using ReLU as the activation function with dropout of 0.3 and the final layer will be using softmax function to output 5 classes. The proposed architecture of the convolutional neural network can be seen below.
![CNN drawio](https://github.com/eethiing/Stationeries-Classification/assets/85276977/a4c8e20c-c0b6-476a-a571-1f0a3e187816)

## Comparison of Experiment Setup
----------------------------------------------------------------------------------------------------------------------
A) Training : Validation : Testing Split Ratio

For Model A, the training set was 70% of the whole dataset, Model B 80% and Model C is 70% with addition of 3500 images that was produced by augmenting the data. The augmentation done here was flipping, random brightness and contrast, and rotating. Based on the results below, Model B's ratio and data will be used throughout the experiment project.

| MODEL   | NUMBER OF DATA IN TRAINING SET | VALIDATION LOSS | VALIDATION ACCURACY | TESTING LOSS | TESTING ACCURACY |
|---------|:------------------------------:|:---------------:|:-------------------:|:------------:|:----------------:|
| A	    | 3500	                         |     0.6970      |        0.8070	     |    0.6728	  |     0.8340       |
| B	    | 4000	                         |     0.5490      |        0.8480	     |    0.5385	  |     0.8280       |
| C	    | 7000	                         |     0.7466	 |        0.8230	     |    0.7725	  |     0.8180       |


B) CNN hyperparameter/Layer

|MODEL| CNN HYPERPARAMETERS/LAYERS | VALIDATION LOSS | VALIDATION ACCURACY| TESTING LOSS | TESTING ACCURACY |
|-----|:----------------------------:|:-----------------:|:--------------------:|:--------------:|:----------------:|
|A	| PROPOSED ARCHITECTURE	     |     0.4907	     |       0.8540	  |    0.5274	   |      0.8480      |
|B	| ADDED AN EXTRA LAYER OF CONVOLUTIONAL AND POOLING  LAYER WITH DROPOUT OF 0.4 |    0.5953       |       0.8600	  |    0.6886	   |      0.8120 | 
|C    |ADDED AN EXTRA LAYER OF CONVOLUTIONAL AND POOLING LAYER WITH DROPOUT OF 0.3 |     0.5490      |       0.8480	        |    0.5385	   |    	0.8280      |


## Results
----------------------------------------------------------------------------------------------------------------------
The figure below shows the training and validation loss and accuracy graphs of the proposed model. The model was trained with epoch=9 since previously the validation loss on epoch=9 was the lowest when trained with epoch=15.
![image](https://github.com/eethiing/Stationeries-Classification/assets/85276977/9d9ed63c-4924-4c52-bca2-6c731f037e58)

Results of classification for each class
| CLASSES | PRECISION | RECALL | F1-SCORE |
|--------|:---------:|:------:|:--------:|
|0 - ERASER	|0.85	|0.83|0.84|
|1 - NOTEBOOK |	0.83|	0.85	|0.84|
|2 - PEN |	0.90	|0.87	|0.88|
|3 - SCISSORS |	0.81|	0.91	|0.86|
|4 – TAPE|	0.87	|0.78|	0.82|


Below presents some of the sample images that was misclassified by the model.
![image](https://github.com/eethiing/Stationeries-Classification/assets/85276977/5d4437cd-1b4d-4224-b336-7dcc86aa61c0)




