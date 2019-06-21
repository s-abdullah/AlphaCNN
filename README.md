# AlphaCNN
Training a CNN on self collected data of alphabets to use in an application
## Data
The data was collected using the front camera of an Ipad. The reason it was done this was was because it was latergonna be used to develop an application for that Ipad.
The data consists of all the English Alphabets that are rotated at 30 degree angles at different positions. 
The model is trained on a data set of around 4,000 images of size 28x28 pixels. The next step is to trian on a bigger data set of 13,000 images of 64x64.
![alt text](https://github.com/s-abdullah/AlphaCNN/blob/master/Images/data.png)
## The Model
A very simple Convolutional Neural Network was used here:
1) 3 Convolutional Layers
2) 2 Fully Connected Layers
3) Hyperbolic Tangent as the activation
4) 0.1 Dropout in Fully Connected layers
5) Log Softmax with ADAM optimizer
![alt text](https://github.com/s-abdullah/AlphaCNN/blob/master/Images/network.png)
## Training results
The model achieved 100% accuracy in training and 87% in testing. 1200 epochs were used for the final model with 28x28 data. 
![alt text](https://github.com/s-abdullah/AlphaCNN/blob/master/Images/accu.png)
![alt text](https://github.com/s-abdullah/AlphaCNN/blob/master/Images/loss.png)
## Use in Application
A simple program was made to leverage the trained model. It loads the models, and takes in a photo of video. 
The imaged is segmented to get the bounding boxes of the letters using contours. The a series of processing steps are taken to make it ready for the network.
Original Input Image:

![alt text](https://github.com/s-abdullah/AlphaCNN/blob/master/Images/real.JPG)

The following image is taken after from the original and thresholded for Blue:

![alt text](https://github.com/s-abdullah/AlphaCNN/blob/master/Images/a4.png)

This is then thresholded into a binary image:

![alt text](https://github.com/s-abdullah/AlphaCNN/blob/master/Images/a2.png)

Then a series of erosions and dilations to remove noise:

![alt text](https://github.com/s-abdullah/AlphaCNN/blob/master/Images/a7.png)

Then it is resized to 28x28:

![alt text](https://github.com/s-abdullah/AlphaCNN/blob/master/Images/a1.png)

The final output of the classification is shown below. It is not perfect and the next steps are to use bigger images and a bigger data steps for a more robust network.

![alt text](https://github.com/s-abdullah/AlphaCNN/blob/master/Images/realTest.jpg)
