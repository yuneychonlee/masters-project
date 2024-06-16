# Masters Research Project 2021
Sensing of the Interactions between the Anaesthesia Face Mask and the Switching Nasal Interface during the Delivery of THRIVE in an Anaesthetic Environment.

![image](https://github.com/yuneychonlee/masters-project/assets/170559075/6606923e-7461-4d9d-a93b-55728af015ba)

## Abstract
Transnasal humidified rapid insufflation ventilatory exchange (THRIVE) is a recently introduced
ventilation technique in the anaesthetic environment. It is a non-invasive technique that provides
a humidified nasal high flow through the nasal interface. Depending on the patient and situations
in the operating theatres, therapies utilising the anaesthesia face mask are required. The invention
of the Optiflow™ Switch Filtered Nasal Interface supports the facilitation of seamless therapy
switching between nasal flow therapy and face mask therapy.

This research project investigates the interactions between the nasal interface and the anaesthesia
mask. A sensing system was proposed to capture quantifiable data for contact force and the 3D
orientation of the anaesthesia mask. A PC software was developed to monitor the sensing system
and inform the user of the successful therapy switching based on the predictive algorithm.

A repeatable therapy switching simulation was set up with the Instron Tensile & Compression
Tester to allow observations of the delta forces experienced at four different locations of the
anaesthesia face mask. A total of 5 tests were conducted for three anaesthesia face masks. The data
analysis formed a basis for the predictive algorithm to determine successful therapy switching.
This algorithm was tested on the manual simulation of therapy switching.

The analysis showed that during the simulation of therapy switching, an average delta contact force
of 3 N was observed at the nasal bridge, and an overall sum of the contact delta forces at the two
sides of the nasal interface and the chin exceeded 7 N. The roll and pitch of the anaesthesia mask
orientation were within ± 2 °. The accuracy of the predictive algorithm to assess the successful
therapy switching was approximately 93% in time agreement to truly switched state.

## Proposed Hardware Design
![image](https://github.com/yuneychonlee/masters-project/assets/170559075/2d91e6e6-7ba9-4a75-bfc6-307383cdab9e)
- The op-amp for the buffer will be the MCP6004 as it is a low power IC and available in a 14-lead quad package that can accommodate the four FSRs.
- The data acquisition hardware will be the Arduino Nano that utilises the ATmega328P microcontroller (MCU).
- A 9-DOF sensor Inertial Measurement Unit (IMU) is also integrated into the system to gather supplemental information from the sensing system. The BNO055 (Bosch Sensortec GmbH, Reutlingen, Germany) is an all-in-one sensor that consists of a MEMS accelerometer, magnetometer, and gyroscope on a single die. The sensor will be connected to the hardware on channels A4 (SDA) and A5 (SCL) for the I2C communication protocol.

### Sensor calibration
Tactile sensing FSRs (force sensing resistors) were calibrated with known values of force by conducting a compression test on the calibrated Instron machine and 500 N load cell.

![image](https://github.com/yuneychonlee/masters-project/assets/170559075/7ede73d0-994e-49b9-83ce-9867d266d591)

## Software
Block diagram of the sensor system integration:
![image](https://github.com/yuneychonlee/masters-project/assets/170559075/53c7ddc2-6f64-479d-881f-5c0727782cf9)

## Demo of PC GUI
Developed on Processing (a graphical library and integrated development environment) is able to track the anaesthesia mask orientation in 3D, present sensor information, and indicate prediction of a successful anaesthesia mask seal. The embedded software outputs the raw data by comma separated values, which can be logged and saved to CSV files. The logged data can be further processed for analysis; for this project a Python script and data analysis library “pandas” is used.
![image](https://github.com/yuneychonlee/masters-project/assets/170559075/88a3bc6b-7041-4bf5-aacd-25473286caa3)

## Example of Data Analysis
Measurement of force in Newtons on various sensing positions on the face mask against the residual flow in L/min.

![image](https://github.com/yuneychonlee/masters-project/assets/170559075/a351d76b-d69e-4ed1-a4f0-cef181397223)

