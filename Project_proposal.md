
# Project Proposal:  Handwritten Mathematical Calculator on FPGA


> Stella Nguemmo, Supriya Kajla


## Overview

In this project we want to implement a handwritten math calculator on the FPGA platform PYNQ-Z2 which performs all Arithmatic operations on numbers. 
                                                              OR
In this project we want to implement a handwritten math calculator on the FPGA platform PYNQ-Z2 which performs Arithmatic operations on decimal numbers.


## Background

In this project, we will try to implement a Handwritten Mathematical Calculator on the PYNQ-Z2 FPGA platform. We can provide an input in the form of a picture stored in the SD card. It will then try to detect elements present in the picture such as possible numbers or mathematical operators, extract these elements separately, and resizes it to a size of (32x32x1). It will use the method of convolutional neural network in order to analyse the picture and finally output an array of size (14x1). There will be a total of these 14 numbers as shown in the below table:


| Number | Meaning  |
| :----: | :------: |
|   0    |    0     |
|   1    |    1     |
|   2    |    2     |
|   3    |    3     |
|   4    |    4     |
|   5    |    5     |
|   6    |    6     |
|   7    |    7     |
|   8    |    8     |
|   9    |    9     |
|   10   |    +     |
|   11   |    -     |
|   12   |    *     |
|   13   |    /     |

Subsequently, we will accept the recognition result of the convolutional neural network, and finally calculate the result of the input.


## Implementation Strategy

This project consists mainly of tree parts: Extracting the numbers and operators from the image; resizing it and then processing the operation.

To extract the elements on the image we're going to use the convolutional neural network (cnn). This will help us in processing the image. We will then use an IP-resize to changes the size of they extracting elements. Afterwards we will accept the recognition result of the convolutional neural network, and finally calculate the result of the input.

First, we plan to use only decimal numbers and simple mathematical operators. Later, we could integrate more complex operators, so that the calculator can handle more elements.

This project consists of only one part: Software_Project.

The Software_Project includes the tensorflow model of this network, pre-trained network parameters and data sets. By the end of this project, we will be able to understand more about the network structure, how to re-train our own parameters or train the network to detect others.
Here are the few steps that will help us in implementing the project on our FPGA platform.

To extract the elements on the image we're going to use the convolutional neural network (cnn). This will help us in processing the image. We will then use an IP-resize to changes the size of they extracting elements. Afterwards we will accept the recognition result of the convolutional neural network, and finally calculate the result of the input.

First, we plan to use only decimal numbers and simple mathematical operators. Later, we could integrate more complex operators, so that the calculator can handle more elements.


Tools required:

Jupyter Notebook
Python 
Tensorflow 1.X
PYNQ-Z2 FPGA Platform
PYNQ-Z2 v2.5 images

## Tasks

1. First we will import all the necessary modules such as tensorflow and keras.
2. Generate HLS IP
3. We will then Load overlay and IP.
4. Insert image Input Path
5. Allocate the memory inbuffer.
6. The step of network data and image pre-processing will be done.
7. Hardware initiation
8. Hardware  control
8. The calculation part takes place where the definition of operators is being analysed and the neccessary calculation is done.
9. The main function is executed and detection of various example images takes place and the result is returned.
10. Run on PYNQ-Z2.  


### Estimated Timeline

* Task 1 (3 hours)
* Task 2 (2 hours)
* Task 3 (2 hours)
* Task 4 (2 hours)
* Task 5 (8 hours)
* Task 6 (2 hours)
* Task 7 (4 hours)
* Task 8 (4 hours)
* Task 9 (3 hours)
* Task 10 (4 hours)

