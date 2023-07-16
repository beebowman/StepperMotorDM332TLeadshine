# StepperMotorDM332TLeadshine
Arduino code to control stepper motor with micro stepper driver such as DM332T Leadshine 

This Github repository folder contains Arduino code that you can use to control a NEMA 23 stepper motor that has been hooked up to a DM332T Leadshine Digital Stepping Driver (Micro Stepper Driver). A micro stepper driver is useful for ensuring very precise control of a stepper motor, since it has the option of setting the pulse/rev (number of pulses per revolution) for the motor so that you can move very fast or very slow and control exactly how many revolutions to turn. 

**YOU WILL NEED: **
- NEMA 23 motor (it can be standalone or it can be attached to a linear guide, either is fine)
- 24V power supply (if it has two bare wires poking out, red and black, then you won't need any adapters. Otherwise, get the power supply adapters below 
- Power Supply Adapters (For example, Female DC Power adapter - 2.1mm jack to screw terminal block from Adafruit.com). You may need to check to make sure that the 2.1mm jack can connect to your 24V power supply; if not, get a connector that has a screw terminal block on one side, and the correct jack size on the other side so that it will connect to the other side of the power supply.
  For example: https://www.adafruit.com/product/368 
- Adafruit Pocket Screwdriver, or equivalent, such as a Digilent screwdriver (you will use the flat side) 
  For example: https://www.adafruit.com/product/3284
  OR: https://digilent.com/shop/digilent-screwdriver/ 
- DM332T Leadshine Micro Stepper Motor Driver (or any other driver with ENA, DIR, PUL, A+, A-, B+, B-). For example it should just have DIR, not DIR+ and DIR-.
- Arduino Uno R3 Board
  For example: https://www.amazon.com/dp/B01EWOE0UU?ref=nb_sb_ss_w_as-reorder-t1_k1_1_8&amp=&crid=1LJBOY44K56S5&amp=&sprefix=arduino+ 
- Arduino Uno connector cable (they are usually blue in color, and connect the board to your laptop via USB)
- Downloaded Arduino IDE software on your laptop
- Arduino Jumper wires (you can buy on Amazon easily)
  For example: https://www.amazon.com/dp/B01EV70C78?ref=nb_sb_ss_w_as-reorder-t1_k0_1_20&amp=&crid=3TSY4TX2UTQYQ&amp=&sprefix=arduino+jumper+wires
- OPTIONAL: Breadboard, LED, and 2k Ohm resistor, can be useful for troubleshooting but definitely not required 

INSTRUCTIONS: 
1) Connect the DM332T, NEMA23 stepper motor, and Arduino to each other using the jumper wires.
   Screw into DM332T
   Connect DM322T to Arduino
   Attach screw terminal block power supply adapter to the Power supply cord (DO NOT PLUG INTO WALL YET!)
   Screw 2 wires into the terminal block part of the adapter, and then into the +Vdc and GND of the DM332T micro stepper driver 
3) Plug in your Arduino IDE to your laptop USB 
4) Copy-paste the code into the Arduino IDE software
5) Ensure that the Board and Port are properly selected in Tools > Board and Tools > Port within the Arduino IDE menu bar. The correct port should show up when you connect the Arduino via USB to your laptop, and will disappear when you disconnect it; that's how you tell which PORT is the right one. For boards, select Arduino AVR Boards > Arduino UNO 
6) Press the checkmark button in the upper left hand of the Arduino IDE interface to check the code (make sure no errors pop up, sometimes if you made a typo in the code, it will alert you of this) 
7) Then, press the right arrow button in the upper left hand of the Arduino IDE to upload the code to the board
9) Lastly, connect the power supply into the wall 
