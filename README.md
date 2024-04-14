## Hexapod

First of all, the program should be done in the SD card, including writing the Raspberry Pi system, 
downloading and installing the Rasptank program. 

Pay attention to the case sensitivity during process of git clone. It will automatically start up at boot after the program is successfully installed. 

You need to connect the driver board and the Raspberry Pi, and before turn it on, connect the servo with the driver board. 
Wait until the servo rotates to specified position to assemble. 

The servo is 20 teeth and will have an error of less than 9° during the installation process, which is normal.

---------------------------------------------------------------------------------------------------------------------------

The .py program in the folder client is the program required on the PC.
The .py program in the folder server is the program required on the robot.

This instruction focuses on the programs in the folder server. When you encounter problems, you can refer to this description to solve the problem.


Try the beta program - a program named serverTest.py in the folder server.
If you need the beta program to run automatically  every time you boot, execute autorun.py - enter "2" to select the autorun beta - enter.
If you need to change to the full version of the autorun program every time you boot, execute autorun.py - enter "1" to select the full version of autorun - enter.


We have reserved an interface for adjusting the direction of the servo in the program, which makes it much more easier to debug.
All motion-related code is written in the program server/move.py.
Enter the following command to open (note that it is not to execute) move.py and edit:
	sudo  nano (path)/move.py
The path of move.py is //home/pi/adeept_raspclaws/server/move.py
After opening move.py, change the value of set_direction to 0 (the default is 1), then press ctrl+x to exit, press Y to save change, and press Enter to confirm.

If the reaction is slow, you can increase the P value appropriately (the line75 of move.py). If the reaction is too fast (or swing back and forth), you can reduce the P value appropriately.
If the reaction speed is normal but there is overshoot, you need to increase the I value appropriately.
The D value is differential and usually does not need to be changed.


