
# Project Proposal:  Handwritten Mathematical Calculator on FPGA


> Stella Nguemo


## Overview

In this project We want to implement a handwritten math calculator on the FPGA platform PYNQ-Z2.

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
|   12   |    *     |
|   13   |    /     |


Then we accept the recognition result of the convolution network and finally calculate the result of the input.

## Implementation Strategy

This project consists of two parts: Software_Project and Hardware_Project.

The Software_Project includes the tensorflow model of this network, pre-trained network parameters and data sets. So if you want to understand more about the network structure, re-train your own parameters or train this network to detect others, you should look at the Software_Project/ folder.

If you want to rebuild the hardware of this project, you need to look the Hardware_Project/ folder and follow my instructions below
Our project falls into three major categories - scraping the data, interacting with the user, and computing the character profile to output to the user.

First, we're going to scrape the [D&D 5e API](http://www.dnd5eapi.co/), which has all of the D&D information, collected from the Player's Handbook and Dungeon Master's Guide. We'll put all of the character, spell, and equipment information into a database so that we can efficiently query it later. For this part, we're going to rely extensively on the `requests` module discussed in class - and perhaps some of the multiprocessing primitives in the standard library to speed up the download.

To interact with the user, we're going to have a simple text-based I/O system where the user enters character information one at a time and then signals when done. We'll then ask more questions (but only the *really* important ones) and output a bunch of potential characters for the user to choose from.

To actually compute the best character profiles, we'll simply filter out all the characters that *don't* match the desired profile. Of the remaining options, we'll sort them on a combination of relevance to the original suggestions and based on self-computed heuristics about character effectiveness. We plan to use the awesome `pandas` library for better data manipulation of the character data in raw Python.


## Tasks

1. Generate HLS IP
2. Load overlay  and IP
3. Insert image Input Path
4. allocated the memory  inbuff
5. weight and bias copyto memory
6. image pre-processing
7. hardware initiation
8. hardware  control
9. implement the calculator 
10. main function to use the calculator
11. Run on PYNQ-Z2



### Estimated Timeline

* Task 1 (3 hours)
* Task 2 (2 hours)
* Task 3 (3 hours)
* Task 4 (1 hours)
* Task 5 (1 hours) - Parth
* Task 6 (3 hours) - both
* Task 7 (1.5 hours) - Michael
* Task 8 (4 hours) - Parth
* Task 9 (5 hours) - Guido
* Task 10 (4 hours) - Parth
* Task 11 (5 hours) - Guido

0

## Resources

In this project, we will be using Microsoft Visual Studio for compilation purposes. Vivado HLS will be used to create block designs. We also need a PYNQ-Z2 FPGA platform and some PYNQ-Z2 images for this project.
