
# Project Proposal:  Handwritten Mathematical Calculator on FPGA


> Stella Nguemo


## Overview

In this project We want to implement a handwritten math calculator on the FPGA platform PYNQ-Z2.

## Background

this calculator is a handwritten calculator. This means that for this calculator, you just have to write the operation you want to perform on paper. After that, it can be photographed and stored on the SD card. The image stored on the SD card will then be used as input for this operation. this image will be retrieved and the various numbers and operators found on this image will be detected and extracted. After all these step, the operation can be carried out.



## Implementation Strategy

This project consists mainly of tree parts: Extracting the numbers and operators from the image resizing it and then processing the operation.

To extract the elements on the image we're going to use the convolutional neural network (cnn). This will help us in processing the image. We will then use an IP-resize to changes the size of they extracting elements. Afterwards we will accept the recognition result of the convolutional neural network, and finally calculate the result of the input.

First, we plan to use only decimal numbers and simple mathematical operators. Later, we could integrate more complex operators, so that the calculator can handle more elements.



## Tasks

1. Generate HLS IP
2. Load overlay  and IP
3. Insert image Input Path
4. allocated the memory  inbuff
5. image pre-processing
6. hardware initiation
7. hardware  control
8. implement the calculator 
9. main function to use the calculator
10. Run on PYNQ-Z2



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



## Resources

In this project, we will be using Microsoft Visual Studio for compilation purposes. Vivado HLS will be used to create block designs. We also need a PYNQ-Z2 FPGA platform and some PYNQ-Z2 images for this project.
