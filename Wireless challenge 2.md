# bi0s Hardware    _____By:Kiran S Pillai 

## **CHALLENGE-2--AM Transmitter and Receiver**
___
### In this challenge we are supposed to make 2 GNU Radio flowgraphs implementing an AM Receiver and Transmitter and test its working.
_____
### **AM TRANSMITTER**
===============  

A device that takes the audio signal as an input and delivers AM wave to the antenna as an output to be transmitted.

### **AM RECEIVER**
===========  

A device that takes the AM wave as an input and produces the original audio signal as an output.

### **Flow graph / Blocks**
================  
These are what replicates real life hardware sources and functions. There are hundreds of blocks which are assigned for each operations and can be made to functions according to users wish. The block are connected to the next one by joining the output of one block to the input of the other. 
The flowgraph mostly starts from one or the other source block(which sends data) and terminate at a sink(which accepts the data).

### The flow graphs used in AM transmitter are :-
>  **_OPTIONS_**
* This block sets the parametrs to the flowgraphs such as title, author, description etc. 
* `id` - This is the name of the file we genarate.
> **_VARIABLE_**
* This block holds the particular value which the user assigns to it. It can be called thorughout the flowgraph.
> **_QT GUI RANGE_**
* This creates a varible with slider which helps the user to vary the input value. We can specify the range uptu which the value should vary. It provides variety of widget option.
> **_AUDIO SOURCE_**
* This block acts as a  microphone input. It takes the data from the device microphone and uses it as per user's program.
* `sample rate` - This can be either specified through the drop down menu which consist of default values or by user defined variables.
* `Device name` - This will be left blank so that software itself will select the microphone or else should mention about the device name.
* `Num Outputs` - This can be used according the requirement. 2 output will result in stereo audio output.
> **_REPEAT INTERPOLATION_**  
* This block repeats each input Interpolation number of times.
* Interpolation=16
> **_MULTIPLY CONST_**
* This block multiplies the input value with the specified constant.
* Constant=1.2 
> **_ADD CONST_**
* This block adds the input value with the specified constant.
* Constant=1.0
> **_MULTIPLY_**
* This block multiples the input values together and send the result as output.
> **_SIGNAL SOURCE_**
* It is a signal generator. Has different type of output options(float, complex,int, etc). Can form different sign forms (sin, cosine, square ,etc).
> **_QT GUI TIME_SINK_**
* This is a graphical sink to display multiple signals in time. It takes set of a float streams and plots them in the time domain. Each signal is plotted with a different color.  
> **_ZMQ PUB SINK_**
* This block acts a a streaming sink for a GNU Radio flowgraph and writes its contents to a ZMQ PUB socket. it basically acts as an medium of communication to send data.

![](https://i.ibb.co/7VQ659f/am-tranmsitter.png)

The noise detected by the device microphone is send as signals to the repeat block, which then send the data by repeating it 16 times. This data is multiplied 1.2 times and is split and fed into QT GUI Time Sink and also to an Add Const block which adds value 1 to the data. This is then sent to multiply block along with in waveform from the Signal source block. The output data is send to QT GUI Time sink as 2nd input, and also to the ZMQ PUB Sink.
___  


### The flow graphs used in AM reciever are :-   

> **_FREQUENCY XLATING FIR FILTER_**
* This block performs a frequency translation on the signal, as well as downsamples the signal by running a decimating FIR filter on it. Its used as a channelizer, to pull out a narrowband portion of a wideband signal. 
>  **_AGC_**
* Automatic Gain Control- it maintains suitable signal amplitude at the output respective to the change in input.
> **_COMPLEX TO MAG_**
* calculates the magnitude of the input comlex values. Basically used to demodulate signals.
> **_BAND PASS FILTER_**
*  A bandpass filter allows signals within a selected range of frequencies to be decoded, while preventing signals at unwanted frequencies. 
> **_QT GUI TIME SINK_**
* This is a graphical sink to display multiple signals in time. It takes set of a float streams and plots them in the time domain. Each signal is plotted with a different color.  
> **_ZMQ PUB SOURCE_**
* This block acts a streaming sink , it fetches the data from the localhost port and sends out the data.
> **_MULTIPLY CONST_**
* This block multiplies the input value with the specified constant.
* Constant=0.3
> **_AUDIO SINK_**
* Allows a signal to be played through the speakers.

![](https://i.ibb.co/mHG2BNT/am-reciever.png)  
The data fetched from the ZMQ PUB socket is send to frequency xlating FIR filter that narrows down the signals and send that to AGC which keeps track of the amplitude and accordingly cocntrol it. The signal i converetd to magnitude and send to bandpass filter which allows only particular range of signals. These signals are send to QT GUI Time sink to mark the time domain representaytion. Also the data is send to audio sink through multiply block with 0.3 as the constant. The sound is played back through device audio output.
___
### **Graphical Representation**
=====================

![](https://i.ibb.co/SnMjJNr/am-transreciever.png])

### _Thank you_

___-KSP___