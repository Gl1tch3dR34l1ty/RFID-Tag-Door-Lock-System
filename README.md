# RFID-Pet-Tag-Door-Lock-System
RFID COSC1030 Group Project

This is a computer science project that was started in order to build to creating a door lock system specifically for a pet door. The goal was to work up to being able to integrate an RFID door lock system with a tag that can be connected to a pet's collar to allow them access through a pet door in order to give them more autonomy when alone.

Link to full instruction document used to start this project (includes how to set up the RFID, create a write and read file, and how to run the write and read files): 
https://srituhobby.com/how-to-make-an-rfid-door-lock-system-with-raspberry-pi-board/?srsltid=AfmBOop11d9lPfGkxk32rNBZU558JenfbhboKhBdjgvasokk8zl277Ms


There were a few issues that were run into while working on this project:

1. When attempting to install and update the packages needed for the project, the terminal would get stuck at a point that said something along the lines of "installing fonts...". After multiple attempts and a lot of research, the best way to get around this was to start over with a new SD card or format the current SD card. We assume that something must have gone wrong with the installations and updates along the way, so instead of trying to fight that, we recommend formatting the SD card or switching to a new one.

2. There was also some trouble getting the LCD screen to display. The fix to that was by using a small object or screwdriver and twisting the potentiometer - the blue box on the I2C module - while running a program that transmits text until the display worked properly.

      A video that was helpful for making sure that the LCD screen was working:
   
      https://www.youtube.com/watch?v=fR5XhHYzUK0

3. The I2C module did not connect properly to the display on its own - it had to be placed in a specific position to provide power to the display. The remedy for this, at least as a temporary fix, was to wedge something like folded paper between the I2C module and the LCD screen board until it would connect properly.


Some notes about the files included in this repository:

"I2C_LCD_driver.py" allows text to be displayed on the LCD screen

"Library install commands.txt" has all of the commands to install the necessary packages

"Scan.py" gives the command to place the tag against the RFID reader to register its ID number

"DLS.py" (DLS stands for "Door Lock System") gives the command to place the tag against the RFID reader to determine whether or not the tag ID matches the one in the code

****Note: Different tags have different ID numbers, so when a tag is registered, its number will have to be copied into line 16 of "DLS.py" to initiate the tag ID number to the Tag_ID variable


Some things to consider moving forward:

1. There is code for a buzzer included in the "Scan.py" and "DLS.py" files, though the buzzer did not work, so that will have to be looked into, if a buzzer is desired

2. The code currently runs through a loop of locking and unlocking whenever the correct card is recognized on the scanner, however, with the goal of this particular project, the optimal outcome would be for the lock to unlock when the card is recognized, then automatically relock after a period of time without having to have the card present.

3. Figure out what motor is needed to power the door lock and, once that part is acquired, get the code to run so that the lock unlocks when the tag is placed against the scanner during the run of the "DLS.py" program

4. Automate the process of scanning in a new tag and adding that tag's ID number into the "DLS.py" code so that TAG_ID doesn't have to be manually initialized

5. Modify the code so that more than one tag can be valid, because, in the code's current state, only one tag can be entered at a time, so even if two tags are read in and given ID numbers, only the one that the TAG_ID variable is set to will be accepted for locking and unlocking


Here is a link to the presentation of this project:

   https://youtu.be/BEzqA0svQmk

Components:

![All Components](https://github.com/user-attachments/assets/fd47dbfc-40d0-411a-a69c-e7da8c449b5b)

Raspberry Pi Board:

   https://www.amazon.com/Raspberry-Pi-Model-Desktop-Linux/dp/B00T2U7R7I?crid=2RDVGDRTC51FZ&keywords=raspberry%2Bpi%2B2%2Bmodel%2Bb&qid=1655634336&sprefix=raspberry%2Bpi%2B2%2Caps%2C1061&sr=8-1&linkCode=sl1&tag=sritutech20-20&linkId=3d3cd395d60b9d316e9dc2025cf1fc2e&language=en_US&ref_=as_li_ss_tl&th=1

RFID Reader Module Kit:

   https://www.amazon.com/gp/product/B07KGBJ9VG/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B07KGBJ9VG&linkCode=as2&tag=sritutech20-20&linkId=d4e69b41cb66b71f02f5c32febcba75b

LCD Screen and I2C Module:

   https://www.amazon.com/SunFounder-Serial-Module-Display-Arduino/dp/B019K5X53O?th=1


Relay Module:

   This one requires a small screw driver and male-to-male jumper wires:
      
   https://www.amazon.com/gp/product/B00LW15A4W/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B00LW15A4W&linkCode=as2&tag=sritutech20-20&linkId=99fdd5daffb4316feaa61dc3a346ba8b
      
   This one only needs male-to-females jumper wires:
      
   https://www.amazon.com/Ferwooh-Channel-Module-Extension-Trigger/dp/B0CZ6VNK65/ref=sr_1_6?crid=2RTWKA7MYS3U2&dib=eyJ2IjoiMSJ9.7qGrQQ7hnKBoPs3iyyWH31vI03NVO71mxUYayPyhy_zVgyWCQHWttWRfcNc1vR-KjOxDejBk7z-TXgJl7JEqnqLofXfnleP48nF1lpVTtebnvjYifw4u3tGS0UHLZDThboNzYUt4u3fCRDrSiteoWIwEzeoLfL99pivf9Y-aNv1Vnt95ReHeAxTF76GmWxwRuFGKgogBumkCsZolEJ8mZI5S_UiVcV20DfsGBGwViCsuVXkhGovvTF15T8YHGQ8773HxRTVffGF2ivxqbwG4q8r6D-DrG8A93DpCA7WBdCY.x3_wVRGFw98ru8Xph9QTPTrE-zcq4mv-9cmbc7liWnQ&dib_tag=se&keywords=relay+module+5v&qid=1747199011&s=electronics&sprefix=relay+module+5v%2Celectronics%2C187&sr=1-6

Buzzers (if you would like to incorporate one):

   https://www.amazon.com/gp/product/B01N7NHSY6/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B01N7NHSY6&linkCode=as2&tag=sritutech20-20&linkId=bb27de34c83c54584673381df91fdc8d

GPIO Extension Board and Ribbon Cable:

   https://www.amazon.com/DGZZI-Breakout-Expansion-Ribbon-Raspberry/dp/B089SXW3HD?crid=243M2YYUVKEB7&keywords=raspberry+pi+gpio+extension+board&qid=1658142367&sprefix=raspeberry+gpio+extension+board,aps,406&sr=8-21&linkCode=sl1&tag=sritutech20-20&linkId=6429a3b36df3a5e5fc7f7dc76db1a8df&language=en_US&ref_=as_li_ss_tl

Breadboard:

   https://www.amazon.com/gp/product/B07DL13RZH/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B07DL13RZH&linkCode=as2&tag=sritutech20-20&linkId=a904a2ae589b9dc10ae7d2fd8a49338e

Jumper Wires:

   https://www.amazon.com/gp/product/B07GD2BWPY/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B07GD2BWPY&linkCode=as2&tag=sritutech20-20&linkId=a5703ab5b4924376a3bb1fb410824aa2&th=1

Electromagnetic Lock:

![Lock](https://github.com/user-attachments/assets/662e789b-b3cc-42cd-8b7e-76d39cdc74a5)

Pictures of Connections for Reference:

Relay Module to Breadboard Wiring:

![Relay Module Wiring](https://github.com/user-attachments/assets/ae2394b8-dad0-430a-9548-3c9a4ca1c415)

Note: The wires that are attached at the back of the relay - blue and yellow at the top right of the picture - are, presumably, to be connected to a motor that would then connect to the lock

I2C Relay to Module Wiring:

![I2C Wiring](https://github.com/user-attachments/assets/6ef414bd-8fc7-4e10-86e5-8103fea9f360)

LCD Display with Proper Wiring:

![LCD Display](https://github.com/user-attachments/assets/64ef6ba0-6135-47b6-beb5-ddba4b9589c3)

RFID Reader Module Wiring:

![RFID Wiring](https://github.com/user-attachments/assets/2881ae8f-ae46-4d24-806a-8f1de84654ca)

Wiring for all Relays and Modules:

![Full Wiring](https://github.com/user-attachments/assets/8243fe54-6d86-4a76-9bd5-19d989dc2291)

Diagram for Wiring:

![Group Project Diagram (1)](https://github.com/user-attachments/assets/15216ac4-991f-4553-9c08-7a136928894f)
