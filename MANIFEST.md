#MANIFEST
-------

Contains a list of each file and its purpose

*   **.gitignore**: 
      extensions of files that are not including in staging or commits
*   ***/Arduino/***: 
      contains all the adruino programs
	* **License Plate.ino**: 
	    The license plate random generator for the 16x2 LCD Display  
* 	***/RaspberryPi/***: 
      contains all the raspberry-pi programs
	* **ball_tracking.py**: 
	  Vision tracking using the connected camera to find circles and uses the coordinates accordingly to send the power to the correct wheels
	* **DS4_Controller.py**: 
	    PS4 Controller thread that controls the motors and sends messages through pipes in python
	* **Distance_Sensor.py**: 
	  Distance Sensor Module that detects how far the car is from an object the sensor detects
	* **Wheel_Control.py**: 
	  Handles the wheels, is basically the middle man between every module that needs to use the motors
	* ***/DS4Controller/***:
	  Contains all the DS4 module files, thats used in "C" wrapping
	  * **\__init__\.py**
	  * ***/src/***:
	    All the DS4 Controller source files.
        * **\__init__\.py**
        * **DS4.c**: 
        	Main c source file for ds4 driver
        * **DS4.h**: 
        	Main c header file for ds4 driver
        * **DS4.i**:
        	Main c interface file that SWIG uses to make connection to the source file to generate python code.
        * **controller.py**:
        	Auto generated python file once SWIG compiles the .c,.i files to make controller.py
        * **init.sh**:
       	Bash script that is used to remove all generated files and recompiles using the SWIG command
        * **setup.py**:
       	Connecting the interface file with the source c file so the SWIG knowns what files to use for wrapping
        * **test.py**:
       		After controller.py is generated, this file is used to test with the controller.
