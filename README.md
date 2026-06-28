# Quick diagnost tool for HP/Agilent/Keysight 3458A multimeters

This repository contant Python application that can be used to troubleshoot and perform tools for 3458A.
It is created to support public guide about this meters available from [xDevs.com lab](https://xdevs.com/).
Guide is available [here](https://xdevs.com/guide/life_with_3458/).

Current Status
--------------
This is initial version for testing and feedback

Installation requirements
--------------
This build was tested with following environment:

* Windows 10 PC
* Python 3.9
* Python libraries : PyQT5, pyvisa, python-vxi11

Usage requirements
--------------
* Configured and working host with either VISA or Python-vxi gateway, such as E5810A/E5810B
* HP/Agilent/Keysight multimeter connected to GPIB and responsive to commands

User guide
--------------
Copy all files into single directory
Run ./main2.py python application
GUI will load with default parameters loaded from hp3458a_config.json

1. Note down your 3458A serial number and GPIB address, connect GPIB cable
2. Configure backend, VISA or LXI/VXI(e.g. using E5810A gateway)       
3. Enter correct GPIB address to the desired DMM                       
4. Click connect button, should go green if all is ok                  
5. 3458A responds only to ID? command, other instruments use *IDN?     
6. Use buttons ERRSTR? multiple times to read back current fault log   
7. DUMP CAL VALUES button reads all calibration constants from 3458    
8. ACAL buttons trigger artifact adjustment function. Use ERRSTR? after
9. RUN SELF-TEST button triggers self test. Use ERRSTR? to check fails
10. Set ACV sync configs 3458A to syncronous mode, helps check A2 PCBA 
11. Read CALSTR? helps to dump user note sometimes stored in CALROM    

![Image](https://xdevs.com/doc/HP_Agilent_Keysight/3458X/diag/hp3458_test2.png)

Glory to Ukraine!
