# Rear Sensor Array
<img src="https://scontent.fcnd1-1.fna.fbcdn.net/v/t39.30808-6/298458887_498804708915637_8418388517832502489_n.jpg?_nc_cat=106&ccb=1-7&_nc_sid=5f2048&_nc_eui2=AeGLFqM6Q4Nl6OvxIF6o3mUhiMYNqIhi20GIxg2oiGLbQX_ZEMJw0kfpHwaDSUm1Dj1jenFUC-DnqTVNBy9s5qns&_nc_ohc=rnUdAryQe0wAX8CNQ18&_nc_ht=scontent.fcnd1-1.fna&oh=00_AfCb7CNnSoUrz6q5vnEu4laZqss6gLH12xEsg7Rm1HpIuA&oe=65422083" width="300px" height="250px">

## Description
The motivation behind this project was to have an ADC as close as to the analog values
that we needed to measure. 

- ! We faced noise issues with measuring analog values at a distance (more than 10cm)
- It is unfortunately inefficient to have just an ADC because it can't communicate via CAN

In order to accomplish this, we came with this idea of a "sensor array" which integrates a mcu to:
- communicate via i2c with an accelerometer
- read via adc linear potentiometers from the coilovers 
- parse and compress data, if possible, in order to reduce CAN overload
- send data via CAN bus to another device which would store it 

We chose the Raspberry Pi Pico as a solution because it is cheap and it can handle all the above requirements with the only exception being CAN communication which we have enabled by using an external library which enables PIOs as CAN ready pins.

## What you will find here
- Firmware - contains the source code for the mcu
- Firmware_receiver - contains the source code of a Pico used as CAN receiver (testing purposes)
- Docs - contains the documentation, which you can also find here
- PCB - contains the KiCAD electrical scheme and PCB design files

Please refer the full documentation of the project here.

## How to run this project 
To compile the project, please refer to the Raspberry Pi Pico documentation [here](https://datasheets.raspberrypi.com/pico/getting-started-with-pico.pdf). There you will find how to install the build system on Windows as well as Linux machines.

To see the PCB files, please install KiCAD from [here](https://www.kicad.org/).

<img src="pcb_img.png" width="50%" height="50%">
<p><i>Please beware of the jokes on the PCB Soldermask. They are greatly appreciated at Formula Student Comptetitions</i></p>

## License
Apache-2.0 License

