# ATtiny ISP programmer shield for Arduino UNO boards

## What

This repo provides you with all necessary info (and files) to build an Arduino shield to program Atmel's **attiny** 𝜇-controllers. For that matter, the underlying Arduino board should be loaded with the ISP-programmer sketch (built-in example).

## Why

Often, one of these "tiny" chips is largely powerful enough for the design of small projects. During the design phase, I however got tired of wiring up things on a breadboard. As (like many people) I was having a spare UNO, which could serve as an ISP programmer, I decided to design a minimalistic shield to fit on top of it.  

## How

The shield has been designed with EAGLE from AutoDesk/CadSoft. The files can be opened with the free version [(download here)](http://www.autodesk.com/products/eagle/free-download). In order to keep things simple, the PCB can be etched single-sided, as the top-layer only contains a couple of short connections (which can easily be replaced by wire-bridges). Only through-hole components have been used in order to make the built also feasible for any beginner. In the [pdf-folder](pdf-files/) of this repo pdf versions of all important EAGLE views are available, for those not wanting to install EAGLE. Pay attention to print the bottom and top-layer layouts **without re-sizing** (1:1). 

## Technical details

### What’s on the board

The board is fit with 3 IC sockets (8, 14 and 20 pin), for the 3 types attiny’s. **Only one should be fit at a time !** On the prototype, pin headers with double functionality have been mounted. Pins on the bottom-side to fit on the Arduino board, and feed-through female headers on the top for easy access of all Arduino connections. 
The push button, is connected to the reset lines of the attiny’s with a 10kΩ pull-up resistor. When the shield is cut correctly, the reset button for the Arduino UNO itself should still be accessible. In order to make the Arduino Uno work as an ISP programmer a 10µF capacitor needs to be connected on its reset-line. 
Three LED’s are available to visualise the correct functionality of the programming procedure.
An optional AVR ISP socket has been foreseen in order to use the shield as stand-alone with a commercial programmer. 

### How things work

First the the ISP-programmer sketch (built-in example) should be loaded to the Arduino UNO board. During that operation, the blue jumper (JP1) should be removed. Select “Arduino Uno” as target board in the tools-menu. Load the ISP-programmer sketch with the “UPLOAD” button. Once loaded, the jumper can be put back to send your a sketch to your attiny 𝜇-controller. 

![ISP example sketch](images/menu_File-Examples.png) ![Board selection](images/menu_Tools-Board.png) ![Upload](images/menu_Sketch-Upload.png)

To load a sketch to your attiny chip, make sure that the correct target board is selected in the tools-menu (you might need to download a specific library -> tools-menu, board manager). This time, use the “UPLOAD USING PROGRAMMER” option from the sketch-menu.

![Programmer selection](images/menu_Tools-Programmer.png) ![Upload Using Programmer](images/menu_Sketch-Upload_Using_Programmer.png) 

The 3 LED’s will tell you how things are going : 
 - Green  : ISP programmer running
 - Yellow : uploading sketch
 - Red    : error  
 
### Proof of concept

So far, I have tested the shield with the below list of 𝜇-controllers : 
 - attiny84
 - attiny85
 - attiny2313
 - attiny4313

 Any pin-compatible 𝜇-controller should work as well :
 - 8-pin  : attiny10/11/12/13/15/22/25/45/85
 - 14-pin : attiny24/44/84
 - 20-pin : attiny2313/4313
 (on condition of using the correct settings in your Arduino programming environment)

## Contributors

If you are having any good suggestions, just drop me a line. 
If feasible, I'll be happy to implement proposed improvements. 
And if you are having lots of time, I'll be happy to share the work with you ;-).

## License

There is no specific license attached to this shield. 
If you like it, have fun with it (at your own risk :-D).
