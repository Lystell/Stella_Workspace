
# Project Proposal:  Handwritten Mathematical Calculator on FPGA


> Stella Nguemmo, Supriya Kajla


## Overview

In this project we want to implement a handwritten math calculator on the FPGA platform PYNQ-Z2 which performs all Arithmatic operations on numbers. 
                                                              OR
In this project we want to implement a handwritten math calculator on the FPGA platform PYNQ-Z2 which performs Arithmatic operations on decimal numbers.

## Background

To perform the calculation, we first need to recognize and extract the numbers and operators in the image stored on the SD card. The images are considered as input to the operation. After extracting these elements the size will be changed to (32x32x1). The convolutional neural network (cnn) finally outputs an array with a size (14 x 1). The meaning of these 14 numbers is shown in the following table:

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
|   12   | $\times$ |
|   13   |  $\div$  |
Number	Meaning
0	0
1	1
2	2
3	3
4	4
5	5
6	6
7	7
8	8
9	9
10	+
11	-
12	*
13	/

Then we accept the recognition result of the convolution network and finally calculate the result of the input.


SUPRIYA 

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

This project consists of two parts: Software_Project and Hardware_Project.

The Software_Project includes the tensorflow model of this network, pre-trained network parameters and data sets. So if you want to understand more about the network structure, re-train your own parameters or train this network to detect others, you should look at the Software_Project/ folder.

If you want to rebuild the hardware of this project, you need to look the Hardware_Project/ folder and follow my instructions below
Our project falls into three major categories - scraping the data, interacting with the user, and computing the character profile to output to the user.

First, we're going to scrape the [D&D 5e API](http://www.dnd5eapi.co/), which has all of the D&D information, collected from the Player's Handbook and Dungeon Master's Guide. We'll put all of the character, spell, and equipment information into a database so that we can efficiently query it later. For this part, we're going to rely extensively on the `requests` module discussed in class - and perhaps some of the multiprocessing primitives in the standard library to speed up the download.

To interact with the user, we're going to have a simple text-based I/O system where the user enters character information one at a time and then signals when done. We'll then ask more questions (but only the *really* important ones) and output a bunch of potential characters for the user to choose from.

To actually compute the best character profiles, we'll simply filter out all the characters that *don't* match the desired profile. Of the remaining options, we'll sort them on a combination of relevance to the original suggestions and based on self-computed heuristics about character effectiveness. We plan to use the awesome `pandas` library for better data manipulation of the character data in raw Python.

Supriya

This project consists of only one part: Software_Project.

The Software_Project includes the tensorflow model of this network, pre-trained network parameters and data sets. By the end of this project, we will be able to understand more about the network structure, how to re-train our own parameters or train the network to detect others.
Here are the few steps that will help us in implementing the project on our FPGA platform.

Tools required:

Jupyter Notebook
Python 
Tensorflow 1.X
PYNQ-Z2 FPGA Platform
PYNQ-Z2 v2.5 images




## Tasks

1. First we will import all the necessary modules such as tensorflow and keras.
2. We will then Load overlay and IP.
3. Allocate the memory inbuffer.
4. The step of network data and image pre-processing will be done.
5. The calculation part takes place where the definition of operators is being analysed and the neccessary calculation is done.
6. The main function is executed and detection of various example images takes place and the result is returned.



### Estimated Timeline

**(Core)**

* Task 1 (1 hours) - both
* Task 2 (2 hours) - both
* Task 3 (0.5 hours) - Guido
* Task 4 (1 hours) - Michael
* Task 5 (1 hours) - Parth
* Task 6 (3 hours) - both

**(Stretch)**

* Task 7 (1.5 hours) - Michael
* Task 8 (4 hours) - Parth
* Task 9 (5 hours) - Guido

We've made a little progress on Task 1 (we acquired an API token), but we haven't used it to connect to the API endpoint yet.


## Resources

All of our data is going to come from the APIs described above, but we're also going to hand-code some test characters for small data sets to make sure the general logic is working. 
