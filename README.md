# RFID-Tag-Door-Lock-System
RFID COSC1030 Group Project

This is a computer science project that was started in order to build to creating a door lock system specifically for a pet door. The goal was to work up to being able to integrate an RFID door lock system with a tag that can be connected to a pet tag to allow them access through a pet door in order to give them more autonomy when alone.

Link to full instruction document (includes how to set up the RFID, create a write and read file, and how to run the write and read files): 
https://srituhobby.com/how-to-make-an-rfid-door-lock-system-with-raspberry-pi-board/?srsltid=AfmBOop11d9lPfGkxk32rNBZU558JenfbhboKhBdjgvasokk8zl277Ms

There were a few issues that were run into while working on this project:

1. When attempting to install and update the packages needed for the project, the terminal would get stuck at a point that said something along the lines of "installing fonts...". After multiple attempts and a lot of research, we found that the best way to get around this was to start over with a new SD card or format the current SD card. We assume that something must have gone wrong with the installations and updates along the way, so instead of trying to fight that, we recommend formatting the SD card or switching to a new one.

2. There was also some trouble getting the LCD screen to display. The fix to that was by using a small object or screwdriver and twisting the potentiometer - the blue box on the I2C module - while running a program that transmits text until the display worked properly.
      A video that was helpful for making sure that the LCD screen was working: https://www.youtube.com/watch?v=fR5XhHYzUK0

3. The I2C module did not connect properly to the display on its own - it had to be placed in a specific position to provide power to the display. The remedy for this, at least as a temporary fix, was to wedge something like folded paper between the I2C module and the LCD screen board until it would connect properly.

Relay to breadboard connection:
![Relay to Breadboard](https://github.com/user-attachments/assets/3b970697-a12a-4109-9361-5b92208c0f6b)
