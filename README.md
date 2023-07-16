# StepperMotorDM332TLeadshine
Arduino code to control stepper motor with micro stepper driver such as DM332T Leadshine 

This Github repository folder contains Arduino code that you can use to control a NEMA 23 stepper motor that has been hooked up to a DM332T Leadshine Digital Stepping Driver (Micro Stepper Driver). A micro stepper driver is useful for ensuring very precise control of a stepper motor, since it has the option of setting the pulse/rev (number of pulses per revolution) for the motor so that you can move very fast or very slow and control exactly how many revolutions to turn. 

**YOU WILL NEED: **
- NEMA 23 motor (it can be standalone or it can be attached to a linear guide, either is fine)
- 24V power supply, with at least 2.5A current (if it has two bare wires poking out, red and black, then you won't need any adapters. Otherwise, get the power supply adapters below
  For Example: https://www.tinkerforge.com/en/shop/24v-4a-ac-dc-power-adapter.html (this is where I got mine - didn't need adapters) 
  For Example: https://www.amazon.com/ALITOVE-100-240V-Adapter-Converter-5-5x2-1mm/dp/B01GC6VS8I/ref=sr_1_1_sspa?crid=18000JNWLWCRJ&keywords=24V+power+supply+2.5A&qid=1689513828&sprefix=24v+power+supply+2.5a%2Caps%2C101&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1
  Make sure your power supply and power supply terminal block adapters fit together
- Power Supply Adapters (For example, Female DC Power adapter - 2.1mm jack to screw terminal block from Adafruit.com). You may need to check to make sure that the 2.1mm jack can connect to your 24V power supply; if not, get a connector that has a screw terminal block on one side, and the correct jack size on the other side so that it will connect to the other side of the power supply.
  For example: [https://www.adafruit.com/product/368](https://www.amazon.com/gp/product/B07JMY5XXT/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1)
  Or this could work: https://www.adafruit.com/product/1328 
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
   Screw the motor connections into the DM332T
     -First, look at the documentation or instructions for the NEMA23 you bought. It should specify which of the 4 colored wires is A+, A-, B+, or B-.
       In my case, A+ was red, A- was green, B+ was yellow, and B- was blue. Don't worry if you switch A+ and A-, the motor will work fine it will just turn i        the opposite direction. 
     -Next, use the flat end of the Diligent (or Arduino Pocket) screwderiver to loosen the screws, if they are not already loose
     -Insert the A+ wire of the stepper motor into the hole correspnoding to the A+ marking on the stepper driver; hold it in place there 
     -Now, use the flat end of the Diligent screwdriver to tighten the terminal block screw clockwise. Keep going until you feel the wire cannot be pulled out.
     Repeat for A-, B+, and B-, pushing the corresponding motor wire into the terminal block hole and tightening it in place with the screwdriver 
   Connect DM322T to Arduino
     Next, connect pin 9~ on the Arduino to the PUL terminal block slot on the DM332T motor driver, using a jumper wire. On the Arduino you just push it in,        and on the DM332T you follow the same process as you used above; the jumper wire should fit into the hole and be possible to tighten into place using the      screwdriver to turn the terminal screw clockwise.
     Connect pin 8 on the Arduino to the DIR terminal block slot on the DM332T motor driver using the same process as above
     Connect pin 7 on the Arduino to the ENA terminal block slot on the DM332T motor driver using the same process as above
     NOTE: there is really no difference between these pins, other than the 9~ has pulse width modulation capability (signified by the ~). I attached to these      pins; if you attach to other pins, you would need to modify my code in the places where I define and call the pin numbers. 
   Attach screw terminal block power supply adapter to the Power supply cord (DO NOT PLUG INTO WALL YET!)
   Screw two wires into the terminal block adapter, and then into the +Vdc and GND of the DM332T micro stepper driver, tightening with the screwdriver
3) Plug in your Arduino IDE to your laptop USB 
4) Copy-paste the code into the Arduino IDE software 
5) Ensure that the Board and Port are properly selected in Tools > Board and Tools > Port within the Arduino IDE menu bar. The correct port should show up when you connect the Arduino via USB to your laptop, and will disappear when you disconnect it; that's how you tell which PORT is the right one. For boards, select Arduino AVR Boards > Arduino UNO 
6) Press the checkmark button in the upper left hand of the Arduino IDE interface to check the code (make sure no errors pop up, sometimes if you made a typo in the code, it will alert you of this) 
7) Then, press the right arrow button in the upper left hand of the Arduino IDE to upload the code to the board
9) Lastly, connect the power supply into the wall 


TROUBLESHOOTING: 
- If your motor is not turning at all, check the LED indicator light on your power supply. If the light is not on, buy a new power supply and/or try another wall plug. In my case, I had to take extension cords off of the wall outlet area, directly plug in the power supply, and then the LED indicator turned on. The LED indicator on the DM332T itself should also turn on to Green, for the motor to be able to turn. If it is not greend, then you power supply wiring to the +Vdc and GND of the DM332T are not connected properly or there is something wrong with the power supply and power supply terminal block adapter. 
- If the motor only turning in one direction, you likely did not set the ENA pin correctly. Make sure you have connected an Arduino PIN to the ENA pin and that you are sending a signal to turn the pin to HIGH that's sending a signal from the Arduino pin 7 to the the ENA pin. This was a big mistake I made; the key is to "pla around" with either sending a signal (or not) to the ENA pin and see if one way or the other makes a difference. In my case, sending a signal to the ENA pin (even though it SEEMED from the instructions that I shouldn't) fixed the problem and allowed the motor to turn both ways.
Here's what the instruction manual for DM332T said: 
"Enable signal: This signal is used for enabling/disabling the drive. High level +5V (NPN control signal) for enabling the drive and low level for disabling the drive. PNP and Differential control signals are on the contrary, namely Low level for enabling. By default it is left UNCONNECTED (ENABLED)."
So it seems like we should not connect anything to ENA, in order to enable the motor's ability to send a direction signal through DIR. BUT, if you read more closely, you see that it says high level +5V NPN control signal is used to enable the drive. So, that means you actually need to control Arduino pin to send a typical (+5V) signal to that pin to enable it for Arduino! Enabling it by unconnecting it onky works for PNP and Differential Control, which we do NOT have in this case. 
