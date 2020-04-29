## Hardware Required
* Slice Mosquito Hot End. Note that the cooling fan, thermistor and heater cartridge are not included and need to be purchased seperatly. If using their thermistor, some tweaking of the Duet3D firmware is required to properly sense temps. It does come with all the 2.5mm screws you will need to mount it.
* All geared parts from the Bondtech BMG, they can be ordered as 'Spare Parts' (or from one of their distributors) on their website and wont cost as much as an entire BMG extruder:
    * Bondtech Gear Set for M5 shaft
    * Spur Gear for the stepper
    * Reduction Shaft with plastic reduction gear
    * M3 Idler Pivot shaft - 32mm (This will be cut down to 24mm and used on idler)
    * 2 x 5mm Bearings
    * Tension adjustment spring and knob
* A NEMA 17 stepper, preferrable a "pancake" 25mm stepper. Longer ones will work but add weight.
* M3 socket head cap screws:
    * 2 x 40mm
    * 4 x 25mm
    * 7 x 10mm
* M3 hex drive flat head screws
    * 5 x 5mm
* 1 x M6 x 5mm flat tip set screw
* 4 x M2.5 x 5mm socket head cap screws (You can use the 2 different lengths from the Mosquito kit, use the 5mm to mount the Mosquito mounting and the longer ones for the fan)
* 2 x M2.5 x 5.5mm brass inserts, such as these: https://www.amazon.com/dp/B07NBPGTY2
* 1 x M3 x 4mm brass threaded insert, such as these: https://www.amazon.com/dp/B077CJV3Z9
* 1 x PC4-M10 Fitting
* Short length of PTFE tubing

## Printing The Parts
Every part has a face that was designed to print down on the print bed to help eliminate the need for supports. the SLT files should correctly orient the parts in your slicer when imported.

The extruder parts were designed to be printed in PETG. The Fan Shoud should only be printed in ASA, ABS or another hight temp filament.

I suggest using these settings:
* 0.4mm nozzle
* 0.2mm layer height
* 3 perimeters (hot melt inserts need some material to melt into)
* 20% Grid infill

# Assembly
## Prepare the Stepper Motor
1. Install the drive gear on the stepper shaft such that the far face of the drive gear is 17mm from the face of the stepper motor. The teeth of the drive gear should point away from the stepper.

## Prepare the Hot End Block
1. Install the magnet in the Hot end Block. It should be a press fit. Verify the magenet polarity with the Dock before installing. You can put the magent flat on a table and press the Hot End Block onto it.
1. The extruder uses a very short length of PTFE tube to guide the filament into the Mosquito. The PTFE needs to be cut for length such that it fits into the 1mm deep pocket on top of the Mosquito, here is how to do that easily:
	1. Start with a longer length of PTFE tube thats easier to handle.
	1. Cut one end square.
	1. Fully insert the square end of the PTFE tube into the bottom of the Hot End Block.
	1. Finally, cut the PTFE to final length by lining up a razor blade with the two locating bumps on the Hot End Block and cutting through the PTFE. The bumps stick out 1mm and act as a guide.
1. With the PTFE tube in place (this helps to prevent the thin walls from melting!), install the M2.5 brass threaded inserts for the Mosquito.
1. Install the M3 threaded insert for the Idler tension knob.
1. Install the Mosquito onto the Hot End Block with the M2.5 x 5mm bolts included with the Mosquito kit. Make sure the heater cartridge/thermistor face the idler side of the extruder.

## Prepare the Idler
1. Place the Bontech idler gear with its two needle bearings into its final location in the idler. The geared section goes away from the dock. Verify with the Hot End Block.
3. Insert the 24mm x 3mm shaft through the assembly so that it does not protrude from either side of the Idler. Some reasonable force is required as these parts are an interfernce fit.

## Assemble the Drive Line
1. Install bearings
2. 

1. 


Use 1 M3 x 10mm screw to bolt the Stepper Frame to the stepper. The bearing seat in the frame and the power connector on the stepper should be pointing in the same direction when you look at the shaft side of the stepper. Place the back of the stepper on the work surface and orient the power connector "up" (following directions in this section reference this orientation).
1. B
1. Place one of the bearings on the back end of the reduction shaft. Install the bearing & shaft into the bearing seat in the Stepper Frame.
1. Install the Bondtech drive gear and second bearing onto the shaft.
1. Install the Idler Tension Bar into its pocket.
1. Place bolts through the front frame: 2 x M3 x 40mm on the left side holes and 2 x M3 x 25mm on the right side.
1. Place the front frame onto the assembly and tighten the 4 bolts. The idler tension arm should swing freely.

## Align the Bondtech Drive Gear
1. Insert a piece of filament through the filament path
1. Observe the drive hob and make sure it is centered on the filament. If not, loosen the set screw on the Bondtech drive gear and adjust its location. If you have issues, make sure both bearings are fully seated. The reduction gear and the drive gear set the effective working length of the shaft, this can be slightly shorter than the distance between the faces of the fully seated bearings. Some play is actually a good thing, this allows the gear to move to the crown of the filament and always be aligned.
1. Tighten the set screw on the drive gear
1. Close the idler and apply gentle pressure with your thumb. Use the reduction gear to drive the filament back and forth. You should observed that the Bondtech idler gear's back face aligns perfectly with the face of the drive gear, indicating both gears are  aligned on the filament. There is sufficient combined slop in the idler assembly to align with the drive gear.

## Final Assembly

1. Screw the M6 set screw into the Dock Receiver and check that it is flush with the face that meets the dock. Check that the receiver slides onto the dock pins and latches correctly.
1. Attach the Dock Receiver to the Stepper Frame with 1 x M3 x 10mm screw.
1. Use the 5 x M3 x 5mm flat head screws to attach the Tool Changer plate to the side of the extruder.
1. Attach the fan mounting plate to the bottom of the extruder with 2 x M3 x 10mm screws.
1. Attach the Fan and Fan Shroud to the fan mounting plate with 2 x M2.5 x 5 mm screws.
1. Install the spring and M3 x 25mm screw through the top hole in the Idler Tension Arm into the threaded insert.
1. Install the heater cartridge and temp sensor in the Mosquito per their directions.
1. Mount the Cable support from the stock V6 extruder to the top of the extruder with 4 x M3 x 10mm screws.

## Wiring
Use the 3 small cable tie mounts to secure the wiring. The heater cartridge wires come up the front face of the extruder and can be combined with both cooling fan and the thermistor. The thermistor connection is short and has to be made in front of the extruder. The other cables are long enough to reach to the top of the extruder to be connected.
