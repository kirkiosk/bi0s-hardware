# Bios Hardware TASK - 2   _____By:Kiran S Pillai 

## 
## **CHALLENGE-1--Frequency Domain Representation of the Soundcard**
___
### In this challenge we are supposed to make a GNURadio flowgraph that takes an audio input from the sound card and maps its frequency domain representation. 


### **What is GNU Radio ?**   
___
![](https://i.ibb.co/X8YFTYH/gnu.png)

GNU Radio is a `free & open-source` software development toolkit that provides signal processing blocks to implement software radios. They can also be used with readily-available low-cost external RF hardware to create software-defined radios, or without hardware in a simulation-like environment. Generally known as "flowgraphs", which are a series of `signal processing blocks` connected together, thus describing a data flow.
These flow graphs can also be written in `c++` and `python` 
_____

### **Flow graph / Blocks**
================  
These are what replicates real life hardware sources and functions. There are hundreds of blocks which are assigned for each operations and can be made to functions according to users wish. The block are connected to the next one by joining the output of one block to the input of the other. 
The flowgraph mostly starts from one or the other source block(which sends data) and terminate at a sink(which accepts the data).

The flow graphs used are:-
>  **_OPTIONS_**
* This block sets the parametrs to the flowgraphs such as title, author, description etc. 
* `id` - This is the name of the file we genarate.
> **_VARIABLE_**
* This block holds the particular value which the user assigns to it. It can be called thorughout the flowgraph.
> **_AUDIO SOURCE_**
* This block acts as a  microphone input. It takes the data from the device microphone and uses it as per user's program.
* `sample rate` - This can be either specified through the drop down menu which consist of default values or by user defined variables.
* `Device name` - This will be left blank so that software itself will select the microphone or else should mention about the device name.
* `Num Outputs` - This can be used according the requirement. 2 output will result in stereo audio output.
> **_FLOAT TO COMPLEX_**
* This will take input as float and convert them to complex and produce output.
* There are two inputs, in which one will be converted as real part of complex number and the second input will be converted as imaginary part.
If only one is given that will result in real part of complex number.
> **_QT GUI FREQUENCY_SINK_**
* This is a graphical sink that displays multiple signals in frequency. It takes set of comlplex continous complesx data and plots the frequency variations.
* `FFT` - size is set to 1024, this determines how many samples have to be passed at a time.
* `Bandwidth` - is set to the sample rate.
* `Num Inputs` - can be varied according to user's requirement. Here its set to 1.  

![](https://i.ibb.co/mt8mgFM/soud-card.png)

The noise detected by the device microphone is send as signals to the float to complex conveter. Which then sends a set of continous complex data to the QT GUI sink,  this blocks then represent the data in graphical form.
___

### **Graphical Representation**
=====================

![](https://i.ibb.co/wSMZWF0/soundcard-graphical-representation.png "Ideal state")
> Ideal state - When no sound is played.

![](https://i.ibb.co/Pc1ghKH/soundcard-2.png "High pitched noise")
> When high pitched voice was played.
### _Thank you_

___-KSP___