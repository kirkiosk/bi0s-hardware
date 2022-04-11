# bi0s Hardware 
-Kiran S Pillai
# **CompatrIoT**
                                                                Project Topic Familiarisation

## Communication Protocols
----
Communication protocols are formal descriptions of digital message formats and rules. They are important in telecommunications systems and other systems because they create consistency and universality for the sending and receiving of messages.

Communications protocols can cover authentication, error detection and correction, and signaling. They are implemented in hardware and software. There are thousands of communications protocols that are used everywhere in analog and digital communications. Computer networks cannot exist without them.

## Types  of Communication Protocols
---
1. Inter system Protocol
    
        The inter-system protocol is used to communicate between two different devices, like communication between computer to microcontroller kit. This is done through an inter bus system.
        
    ![](https://www.elprocus.com/wp-content/uploads/Inter-Bus-System.png)

    This mainly includes protocols such as:

    * UART Protocol
    * USART Protocol
    * USB Protocol
    
    Lets look more into `"UART PROTOCOL"`.

    ### UART
    ---
    UART[`U`niversal `A`synchronous `T`ransmitter and `T`eceiver]. It is not a communication protocol but just a physical piece of hardware which converts parallel data into serial data. Its main purpose is to transmit and receive data serially.

     UART transmits data asynchronously, which induces that no clock signal is associated in transmitting and receiving data. Instead of clock signal, UART embed start and stop bits with actual data bits, which defines the start and end of data packet. 

     When receiver end detects the start bit, it starts to read the data bits at specific baud rate meaning both transmitting and receiving peripherals should work under same baud rate. 
     

    ### Modes Of UART Communication
    - `Simplex` - Only on one direction (a transmitter to a receiver or vice-versa)
    - `Half Duplex` - Devices take turns transmitting and receiving.
    - `Full Duplex` - Devices can send and receive simultaneously.

    ### DATA Packet Analysis
    ![](https://deepbluembedded.com/wp-content/uploads/2018/09/UART-Data-Packets.png?ezimgfmt=ng:webp/ngcb6)

    - START BIT -  When no data is transmitted the TX is held HIGH(1) and when the data is to be transmitted the UART pulls-down the transmission line from high to low for one clock cycle. Thus the receiving UART detects the high to low transition and begins to read the incoming bits.

    - DATA BITS - Actual data to be transmitted. LSB is default.

    - PARITY BIT -  Allows the receiver to check the correctness of the received data(Rarely used).
        - If parity bit is a 0 (even parity), then number of bits with a value of 1 should sum-up to an even number. 
        - If parity bit is a 1 (odd parity), the number of bits with a value of 0 should sum-up to an odd number.
    - STOP BIT - Is used to indicate the end of the data packet being sent and thereafter the line is held high.
    ---


2. Intra system Protocol
    
        The Intra system protocol is used to communicate the two devices within the circuit board.  In embedded systems, this protocol increases the number of components connected to the conroller which increases the circuit complexity and power consumption. Intra system protocol promises secure access of data from the peripherals.
    
    ![](https://i.ibb.co/7KQztHx/6.png)

    This mainly includes protocols such as:

    * I2C Protocol
    * SPI Protocol
    * CAN Protocol

    Lets look more into `"I2C PROTOCOL"`and `"SPI PROTOCOL"`.

    ### I2C 
    ---
    The inter-integrated circuit is a way of serial communication between different devices to exchange their data with each other. It is a half-duplex bi-directional two-wire bus system for transmitting and receiving data between masters and slaves. These two wires are Serial clock line(SCL) and Serial data line(SDA).
    
    Since this is a master to slave communication protocol. Each slave is been provided with unique address. In order to establish communication, master device initially sends the target slave address along with R/W (Read/Write) flag. The corresponding slave device will move into active mode leaving other devices in off state.
    
    Once the slave device is ready, communication starts between master and slave devices. One bit acknowledgment is replied by the receiver if transmitter transmits 1 byte (8 bits) of data. A stop condition is issued at the end of communication between devices. 

    ![](https://i.ibb.co/R7sqvzH/spi.png)

    ### DATA Packet Analysis

    ![](https://i.ibb.co/M6QfSRj/spi2.png) 

    - START CONDITION - Before transmission starts the SDA line is pulled from HIGH to LOW voltage level before the SCA line is pulled low. With this condition all slaves get active and wait for the address bit.
    - ADDRESS BLOCK - Consists of 7 bit addresses of the slave device. Each slave then compares with these.
    - READ/WRITE BIT - Specifies direction of transfer. The bit is set to '0' when the master needs to send data to slave, and the bit is set to '1' when the master needs to get data from the slave.
    - ACK/NACK BIT - If the physical address of any slave coincides with the address send by the master, the value of this bit is set to '0' by the slave device, or else it remains '1'(default).
    - DATA BLOCK - Consists of 8 bit of data the user sends.
    - STOP CONDITION - After completely tranfering data the SDA line is pulled to HIGH voltage before SCL line is switched from HIGH to LOW.
    

    ### SPI
    ---

    SPI(`S`erial `P`eripheral `I`nterface) is a master-slave synchronous serial communication protocol that provides full-duplex communication at very high speeds as well as simple and low cost interface between a microcontroller and its peripherals.

    In SPI protocol, the devices are connected in a Master-Slave relationship in a multi-point interface, i.e one device is considered the Master and all the other devices are considered as slaves.

    The master first configures the clock using a frequency.The master then selects the particular slave device for communication by pulling the chip select button. That particular device is selected and starts the communication between the master and that particular slave. The master selects only one slave at a time.

    ![](https://www.totalphase.com/media/blog/2020/06/SPI-flow-chart-.png)

    ![](https://aws1.discourse-cdn.com/arduino/original/4X/e/d/c/edc3bb93181f3893bf165d62aa78a41542dd4870.gif)

## JTAG
---
JTAG(`J`oint `T`est `A`ction `G`roup) is a common hardware interface that provides your computer with a way to communicate directly with the chips on a board. The JTAG interface gives manufacturers a way to test the physical connections between pins on a chip. It gives direct hardware access to a device.


## Basic JTAG Architecture
![](https://www.allaboutcircuits.com/uploads/articles/jtag-part-i-introduction-and-the-test-access-port-tap-SG-aac-image1.jpg)

All JTAG-compliant devices must have:

* Test data input (TDI) pins
* Test data output (TDO) pins
* A test clock pin (TCK)
* A test mode select pin (TMS) for controlling the TAP state machine
* TRST - Test Reset (optional)

**Test process**

The standard test process for verifying a device or circuit board using boundary-scan technology is as follows:

1. The tester applies test or diagnostic data on the input pins of the device.
1. The boundary-scan cells capture the data in the boundary scan registers monitoring the input pins.
1. Data is scanned out of the device via the TDO pin, for verification.
1. Data can then be scanned into the device via the TDI pin.
1. The tester can then verify data on the output pins of the device.

____

##### *You hav reached the end of the document*
___

    