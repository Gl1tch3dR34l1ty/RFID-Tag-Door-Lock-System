# RFID-Pet-Tag-Door-Lock-System
RFID COSC1030 Group Project

This is a computer science project that was started in order to build to creating a door lock system specifically for a pet door. The goal was to work up to being able to integrate an RFID door lock system with a tag that can be connected to a pet tag to allow them access through a pet door in order to give them more autonomy when alone.

Link to full instruction document (includes how to set up the RFID, create a write and read file, and how to run the write and read files): 
https://srituhobby.com/how-to-make-an-rfid-door-lock-system-with-raspberry-pi-board/?srsltid=AfmBOop11d9lPfGkxk32rNBZU558JenfbhboKhBdjgvasokk8zl277Ms

There were a few issues that were run into while working on this project:

1. When attempting to install and update the packages needed for the project, the terminal would get stuck at a point that said something along the lines of "installing fonts...". After multiple attempts and a lot of research, the best way to get around this was to start over with a new SD card or format the current SD card. We assume that something must have gone wrong with the installations and updates along the way, so instead of trying to fight that, we recommend formatting the SD card or switching to a new one.

2. There was also some trouble getting the LCD screen to display. The fix to that was by using a small object or screwdriver and twisting the potentiometer - the blue box on the I2C module - while running a program that transmits text until the display worked properly.
      A video that was helpful for making sure that the LCD screen was working: https://www.youtube.com/watch?v=fR5XhHYzUK0

3. The I2C module did not connect properly to the display on its own - it had to be placed in a specific position to provide power to the display. The remedy for this, at least as a temporary fix, was to wedge something like folded paper between the I2C module and the LCD screen board until it would connect properly.

Some notes about the files included in this repository:
"I2C_LCD_driver.py" allows text to be displayed on the LCD screen
"Library install commands.txt" has all of the commands to install the necessary packages
"Scan.py" gives the command to place the tag against the RFID reader to register its ID number
"DLS.py" (DLS stands for "Door Lock System") gives the command to place the tag against the RFID reader to determine whether or not the tag ID matches the one in the code
      Note: Different tags have different ID numbers, so when a tag is registered, its number will have to be copied into line 16 of "DLS.py" to initiate the tag ID number to the Tag_ID variable

There is code for a buzzer included in the "Scan.py" and "DLS.py" files, though the buzzer did not work, so that will have to be looked into, if a buzzer is desired

The code currently runs through a loop of locking and unlocking whenever the correct card is recognized on the scanner, however, with the goal of this particular project, the optimal outcome would be for the lock to unlock when the card is recognized, then automatically relock after a period of time without having to have the card present.

Moving forward, the next major step for this project would be figuring out what motor is needed to power the door lock and, once that part is acquired, getting the code to run so that the lock unlocks when the tag is placed against the scanner during the run of the "DLS.py" program

Here is a link to the presentation of the project:
https://youtu.be/BEzqA0svQmk

Relay to breadboard connection:
![Relay to Breadboard](https://github.com/user-attachments/assets/3b970697-a12a-4109-9361-5b92208c0f6b)
Note: The wires that are attached at the back of the relay are, presumably, to be connected to a motor that would then connect to the lock
