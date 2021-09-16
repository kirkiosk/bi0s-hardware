# Bios Hardware TASK - 2   _____By:Kiran S Pillai 
# _flag={PdLG}_
## 
## **CHALLENGE-2--_7Sniff_**

>In this challenge we have to find the flag displayed by the 7 segment display, but due to faulty display we were unable to view the flag properly.
So by tapping the connecction between the 7 segment display and the shift register we obtained some values.

>### The values are:
>66,56,43,115,142,28,238,188,18,206,123,28,188.

>**HINT**: **Tinkercad loves LSB first.**

---

### **How a 7 segment display works**  
==========================   
![](https://i.ibb.co/WVXQcpM/7SegP.png).

The binary number recieved by the 7 segment display is interpretated in such a way that led at position **a** is turned **ON** or **OFF** by first bit of binary whether its **1** or **0** similarly all other led's will be controlled by rest other binary bits.
_____

### **Shift register 74HC595**
==================

Shift register has 3 input pins and 8 output pins. This recieves data one at a time, using a clock timer each time data is recieved this triggers the clock high and sets back low when not recieving. The bits in the Shift Register move one step to the left.(ex: Bit 7 accepts the value that was previously in bit 6, bit 6 gets the value of bit 5 etc)

![](https://i.ibb.co/xXqHzSh/74-HC595-Shift-Register-Working.gif)

### _**Working**_ 
=======

Using the [Tinkercad Circuit](https://www.tinkercad.com/things/8h5UOY9PFln-copy-of-flag-finder/editel?sharecode=nlTZU2Xx5JOg0ht1CyifR44z_I2QZLwAOcahPcEQ5FA) we hav designed a connection between arduino UNO, shift register, and 7 segment lcd display. Here the given data is assigned into an array and those values are send one by one to the shift register using a using a shiftout(), this function takes in the value and send out the binary format with one bit at a time and then from the shift register this value all together is sent to the 7 segment display which then displays the corresponding character.
___

## Screen shot of **CODE**
===================================

![CIRCUIT](https://i.ibb.co/7gyc56Q/code.png)

___

## Screen shot of **_flag being displayed_**
===================================

![](https://i.ibb.co/n3Mz52D/flag.jpg)

![](https://i.ibb.co/4K4tkk8/pdlg.jpg) 
>The segment diplayed some invalid characters too, so the respecctives data is considered as junk values and is is not taken into account . Also it was given that.

>`Flag format is {FLAG=....}`

>So when we consider only the valid characters we have 4 characters as the flag.
___

# _flag={PdLG}_

### _Thank you_

___-KSP___