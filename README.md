# RemoteRecoverySwitch
Rocket Remote Recovery Switch v1.0

## Overview
The Remote Recovery Power Switch is intended to eliminate the need for a ladder when powering on or arming electronics in tall rockets. We are not anti-ladder, but powering on avionics with your feet firmly on the ground is safer, faster, and a lot less hassle. It also has no mechanical switches to control on-off, so there is no risk of switch bounce or vibration induced brown-outs after launch. If you are on a ladder on a tall rocket and you power-on avionics or sustainer flight computers and they go boom (it happens) then you are in a compromised position.

See the attached Overview PDF for more details and how to use the board.

## Basic Functionality 
The Remote Recovery Switch (RRS) connects between the main battery supplying power to a rocket altimeter and contains a basic “flip flop” circuit that turns the power on and off using a MOSFET. The signal to command on or off is provided by a three wire umbilical that hangs down the side of the rocket and disconnects on launch. Momentarily touching power to the ground-on wires turns it on and ground-off wires turns it off. Any 9v battery or 4-15v source pulse will turn it on/off. The external signal is fed to an optical relay to “air gap” the external signal from the flip flop circuit. Also, the board has two identical flip flop circuits to support two redundant altimeters. Each circuit is fully air gapped to eliminate any single points of failure in flight.     

## Installation
Typically, the Remote Recovery Switch sits between the two rocket altimeters on the same avionics bay sled. A jumper is fed to the 3 pin JST Pad connector to the outside of the rocket. An external connector, as small as a 1mm JST 3 connector pin, can be used to run a wire down the rocket. If the jumper to the outside or the external wire is shorted or damaged in any way it will have no effect on the switch during flight, since a positive voltage pulse is required to command on/off.

## Bench Testing / Manual Switching
The board has a pair of pads marked “ON” on each side to manually power on the altimeter. These do not need a voltage pulse, only a momentary short. They also have an “OFF” pair of pins that are connected to a JST connector. If you short these pins it will turn off. 

## Range and Field Operation
On the range, when you are ready to power up your altimeters you simply touch the gnd-ON wires to a 9v battery, listed for your beeps (or verify other ways), and then launch the rocket when ready.

In the field, you can bring the same wire connector with you and just “pulse it off” or you can install an OFF switch externally using the off JST connector – that is not recommended, since any switch has the possibility to “bounce” during launch and shut off your power, but exposing two pins externally for each altimeter could be an easier way to shut off the rocket in the field, since it does not require a battery – only a short. 

## Ordering from JLCPCB
You need three files to order an assembled PCB. You need 1) the PCB board gerber file that describes the PCB, 2) the bill of materials (BOM) detailing all the little parts that go on the board, and 3) the Pick and Place file that describes where on the board the robots should place the parts.
These three files are in the ordering folder on GitHub.
You can place your own order to JLC-PCB and buy five assembled boards for about $100 (pcb, assembly, shipping, and tariffs as of Dec 2025). 
Here are the rough instructions for ordering your own boards:

•	Go to the JLCPCB order page:  https://cart.jlcpcb.com/quote?spm=Jlcpcb.Homepage.1006

•	Click upload Gerber -- upload the zip file

•	Keep all the default settings

•	Minimum quantity for the basic PCB board is 5

•	Click the PCB assembly switch to on (near bottom of the page)

•	Keep all the defaults, except change quantity (2 min or five)

•	Click NEXT on the right side – it takes you to the PCB

•	Click Next on PCB takes you to the BOM page

•	Click "Add BOM file" - upload the BOM2.xls file

•	Click "Add CPL" - upload the pick and place file

•	Click "Process BOM and CPL"

•	It will give you an error:  The below parts won't be assembled due to data missing. P1,P2,P3,P4,U11,U10,U12,U14 designators don't exist in the BOM file.

•	Click continue on the error -- that is normal, we intentionally omit some parts for assembly

•	At the top of the BOM list it should say "Total 12 parts detected, 12 parts confirmed" // if they do not have stock in a part you will need to swap it for an exact replica part with the same footprint. The older this file gets (from Dec 2025) the more likely the parts turn over at JLC. Resistors and capacitors are usually very easy to replace. As are the LEDs, JST plugs, diodes, and transistors. 

•	Once the BOM is complete click Next to go to the Component Placement page. If the components look like they are on top of the PCB it should be good. Click Next to go to the Quote and Order page.

•	Click Save to Cart and proceed to check out

