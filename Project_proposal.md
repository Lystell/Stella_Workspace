
# Project Proposal:  Handwritten Mathematical Calculator on FPGA


> Stella Nguemmo


## Overview

In this project We want to implement a handwritten math calculator on the FPGA platform PYNQ-Z2.

## Background

To perform the calculation, we first need to recognize and extract the numbers and operators in the image stored on the SD card. The images are considered as input to the operation. After extracting these elements the size will be changed to (32x32x1). The convolutional neural network (cnn) finally outputs an array with a size (14 x 1). The meaning of these 14 numbers is shown in the following table:

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
2. Block Design in Vivado
3. Run on PYNQ-Z2

5. Authenticate to the D&D 5e API
6. Download all of the character, class, race, spell, and equipment information into a database
7. Load the data into Python classes: `Character`, `Class`, `Race`, `Equipment`, `Spell`
8. Main loop that asks user for characteristics and returns character objects using the class interface
9. Match character specifications to classes, races, equipment, and spells
10. Sort remaining characteristics by a "good" heuristic (we'll need to try a lot of heuristics)
11. *(Stretch)* Use common descriptional substitutions and word misspellings for more flexible user input
12. *(Stretch)* Map the characters into a high-dimensional vector space and run clustering algorithms to find the best-matching character profiles
13. *(Stretch)* Use generative adversarial networks to generate images of the character's face. Currently I had to draw this myself:
<p align="center">
	<img src="Kali.png" width="300" alt="Parth's D&D Character." />
</p>

Honestly, the only part we're worried about is the actual algorithm of choosing the best matching character. Can a naive algorithm do "well enough," or do we need to incorporate ML techniques to get reasonable results? We're fairly confident that we can scrape the character data and do the console I/O.


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
