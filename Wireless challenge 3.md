# bi0s Hardware    _____By:Kiran S Pillai 

## **CHALLENGE-3--I/Q Signals**
___

### **What are I/Q Signals ?**   
* The term I/Q stands for **`I`** denoting **`In-phase`** and **`Q`** for **`Quadrature`**. The term phase is relative, and something can only be “in phase” or “out of phase” when reffering with another signal. 
* “In-phase” and “Quadrature” indicates two sinusoids with same frequency and are 90 degree out of phase.
* Being I signal a cosine waveform and Q signal a sine waveform we can say that they both are in _quadrature_, since sine wave is already shifted by 90 degree relative to a cosine wave.  

![](https://in.tek.com/-/media/sites/default/files/u811871/what20iq20image204.png)
___

### **I/Q modulation**
1. **Amplitude Modulation**  
* Modulation can be done by varying the amplitude alone of I and Q indicidually and summing them together.
* A signal will increase or decrease in amplitude if it is created by adding together two signals that are both increasing or both decreasing in amplitude.
* For example: If I and Q signal of same amplitude are then the resulting sinusoid will have the phase in between the phase of I and Q signal.
![](https://www.allaboutcircuits.com/uploads/articles/RFT_ch5_pg4_IQsum.JPG)

2. **Phase Modulation**
* This can be achieved by varying the amplitude of I/Q signal non identically, i.e. changing the amplitude of each signal independantly.
* Increasing amplitude of one waveform with respecct to the other one will result the resultant signal to shift towards the higher amplitude waveform.  
![](https://www.allaboutcircuits.com/uploads/articles/RFT_ch5_pg4_shifttowardI.JPG "Amplitude of I>Q")  
`Here I is greater than Q, hence the resultant is towards I.`
![](https://www.allaboutcircuits.com/uploads/articles/RFT_ch5_pg4_shifttowardQ.JPG "Amplitude of Q>I")  
`Here Q is greater than I, hence the resultant is towards Q.`
___
### **Quadrature Modulation**
This kind of amplitude modulation upon summation of two signals which are in quadrature will result in I/Q signals with phase shifts beyond 90 degree. 

**Process**

![](https://www.allaboutcircuits.com/uploads/articles/RFT_ch5_pg4_QPSKdiagram.jpg "QPSK")  

Digital data stream is covertetd to parallel bits and sent simultaneously. The local oscillator generates the carrier sinusoid from which the I signal is the local oscilator output itself. A 90 degree phase shift is applied to the other part that of Local oscillator to result in Q carrier. THE I and Q signals are multiplied with the I and Q carriers which is then summed to produce the _`Quadrature Phase Shift Keying`_ (QPSK) waveform.

If the I and Q signals are varying from negetive voltage to positive voltage(bipolar), then the amplitude modulation will result in a inversion  since negetive value mutiplied with carrier will result negetive.

#### This will create four different states
1. I normal and Q normal
1. I normal and Q inverted
1. I inverted and Q normal
1. I inverted and Q inverted

The summation of these states will result in :  
#### CASE 1 (phase shift of `45 degree`)
![](https://www.allaboutcircuits.com/uploads/articles/RFT_ch5_pg4_InormalQnormal.JPG "I normal and Q normal")  

#### CASE 2 (phase shift of `135 degree`)  
![](https://www.allaboutcircuits.com/uploads/articles/RFT_ch5_pg4_InormalQinverted.JPG)  

#### CASE 3 (phase shift of `155 degree`)
![](https://www.allaboutcircuits.com/uploads/articles/RFT_ch5_pg4_IinvertedQnormal.JPG)  

#### CASE 4 (phase shift of `315 degree`)
![](https://www.allaboutcircuits.com/uploads/articles/RFT_ch5_pg4_IinvertedQinverted.JPG)  
___

### **Quadrature Demodulation**
Its the reverse process of modulation. By mixing an RF signal with local oscillator signals in quadrature, I and Q signals can be created.
![](https://wiki.gnuradio.org/images/thumb/5/5d/IQ_complex_tutorial_IQ_Mod_Demod-crop.png/1200px-IQ_complex_tutorial_IQ_Mod_Demod-crop.png)
___

### Advantages of Quadrature Amplitude Modulation
1. Due to high data rate large number of bits can be carried by the carrier signal.
1. Low noise interference.
1. Widely used in radio communication, TV broadcast, WiFi etc.
___
### Reference
* https://wiki.gnuradio.org/index.php/IQ_Complex_Tutorial
* https://in.tek.com/blog/quadrature-iq-signals-explained
* https://www.allaboutcircuits.com/textbook/radio-frequency-analysis-design/radio-frequency-demodulation/understanding-i-q-signals-and-quadrature-modulation/
* https://www.elprocus.com/quadrature-amplitude-modulation/
___
### _Thank you_

___-KSP___

