# About 
This is an tool designed for the E3D Tool Changer platform. It used the Bondtech Mini Gear (BMG) drive parts and the Slice Engineering Mosquito for a compact and light weight direct drive tool head. The Project was designed in OnShape and you can get the 

* CAD file in [Onshape](https://cad.onshape.com/documents/296b560eee7721bd4ef989d0/w/77731089a76ed16562e3d253/e/473682607ad5dddc5a373102)
* Discussion thread is here: [BMG + Mosquito + Tool Changer](https://forum.e3d-online.com/threads/bmg-mosquito-tool-changer.3411/)
* STL files and these instructions are maintained on [GitHub](https://github.com/garethky/Slice-Mosquito-Direct-Tool-Head), you can also file an issue there.

This work is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/?ref=ccchooser)

## Goals
* Geared direct drive - smaller stepper means lighter weight tool head which can print faster.
* Use the stock dock in its stock location
* Keep the nozzle location as close as possible to the stock location to enable sharing of wipers and preserve print volume. (tested as within 0.7mm in Z)
* Keep mass near the center of the kinematic coupling to limit wobble and print artifacts.
* Light weight. Measured as 375g with a 25mm stepper including tool changer plate.

## Project Status: Prototype
Currently this project is a prototype. Several things are untested or need to be evaluated, including:
* The cooling fan location, orientation and the fan shroud design.
* The Front Frame gets close to the heat block. Testing is needed to make sure its safe from melting at high temps.
* Bolts engage with the stepper to a depth of 4mm with an intended safety margin of 1mm. If we find steppers with shallower holes than 5mm this engagement should be adjusted for clearance
* General tolerances of bolt heads and shafts are tunable in the design. They print acceptable on my Prusa MK3S but might not have enough tolerance for your printer.

## Known Issues
* The Fan Shroud design is very much a prototype and needs supports to print.
* The bearing seat on the Stepper Frame prints face down and is still having issues printing cleanly without supports.
* The thermistor connector is in an awkward spot an may need an additional cable hold down.

## Hardware Required
* Slice Mosquito Hot End. When you go to buy one, note that the cooling fan, thermistor and heater cartridge are not included. If using their thermistor, some tweaking of the Duet3D firmware is required to properly sense temps. It does come with the 2.5mm screws you will need to mount it.
* All geared parts from the Bondtech BMG, they can be ordered as 'Spare Parts' on their website and wont cost as much as an entire BMG extruder:
    * Bondtech Gear Set for M5 shaft
    * Reduction Shaft with plastic reduction gear
    * M3 Idler shaft - 20mm
    * M3 Idler Pivot shaft - 32mm
    * Spur Gear for the stepper
    * 2 x 5mm Bearings
    * Tension adjustment spring and knob (ditch the plastic washer)
* A NEMA 17 stepper that is at least 25mm long. Longer ones will work but add weight.
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
Every part has a face that was designed to print down on the print bed to help eliminate the need for supports. A couple of spots require some bridging and could be improved.

I suggest using these settings:

* 4 perimeters - The front frame that holds up the Mosquito, in particular, needs the extra wall thickness to not flex
* 20% Grid infill

In addition to these parts you will need the [V6 Cable Support](https://github.com/e3donline/ToolChanger/blob/master/V6%20Tool/STLs/V6%20Cable%20Support.stl) and the [V6 Dock Cables(Mirror).stl](https://github.com/e3donline/ToolChanger/blob/master/V6%20Tool/STLs/V6%20Dock%20Cables%28Mirror%29.stl) (alternately you can not use the Dock Cables for routing the PTFE tube)

### Fan Shroud Special Notes
* Use ASA or ABS
* Fan Shroud requires supports under the two mounting legs. You can use support enforcers in your slicer or set the support angle limit to something small like 10 degrees.

# Assembly
## Prepare the Stepper Motor
1. The stepper shaft needs to be cut so that it is at most 20mm long. If not cut, the shaft will collide with the Mosquito and you wont be able to assemble the extruder.
1. Install the drive gear on the stepper shaft such that the far face of the drive gear is 17mm from the face of the stepper motor. The teeth of the drive gear should point away from the stepper.

## Prepare the Front Frame
1. The extruder uses a very short length of PTFE tube to guide the filament into the Mosquito. The PTFE needs to be cut for length such that it fits into the 1mm deep pocket on top of the Mosquito, here is how to do that easily:
	1. Start with a longer length of PTFE turbe thats easier to handle.
	1. Cut a point in one end of the PTFE to fit the Bondtech drive area.
	1. Install the PTFE in its final location and check alignment and stick-out with the Bondtech gear on the reduction shaft. 
	1. Then cut the PTFE to final length by lining up a razor blade with the two locating bumps on the Front Frame and cutting through the PTFE. (The bumps stick out 1mm)
1. With the PTFE tube in place (this helps to prevent the thin walls from deforming!), install the M2.5 brass threaded inserts for the Mosquito.
1. Install the PC4-M10 Fitting into the top of the Front Frame
1. Install the M3 threaded insert for the tension mechanism (located adjacent to the PC4-M10 Fitting)
1. Install the Mosquito into the Front Frame with the M2.5 x 5mm bolts included with the Mosquito kit. Make sure the heater cartridge faces the front of the extruder (should be the face that was down when the part was printed)

## Prepare the Idler Tension Bar
1. Install the M3 x 32mm shaft (the long one) in the pivot of the tension mechanism. The shaft should be centered.
2. Place the Bontech idler gear with its two needle bearings into its final location in the idler.
3. Insert the short shaft through the assembly so that it does not protrude from either side of the plastic part.

## Assemble the Drive Line
1. Use 1 M3 x 10mm screw to bolt the Stepper Frame to the stepper. The bearing seat in the frame and the power connector on the stepper should be pointing in the same direction when you look at the shaft side of the stepper. Place the back of the stepper on the work surface and orient the power connector "up" (following directions in this section reference this orientation).
1. Bolt the Mid Frame to the stepper frame with 1 x M3 x 25mm screw placed in the lower right corner.
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

# Setup Notes
I used the thermistor from the V6 hot end kit so I wouldn't have to mess with calibrating the one from Slice Engineering.

This tool sticks out further from the dock than the stock V6 tool. You'll need to edit `tpreN.g` and `tfreeN.g` to change the location where the tool is collected. Please don't copy directly and send me hate mail, use the calibration procedure to work out the correct offsets for your printer.

tpreen.g
```
;Move in
G1 X214.5 Y220 F50000

;Collect
G1 X214.5 Y233 F2500
```

tfreen.g
```
G53 G1 X214.5 Y220 F50000
G53 G1 X214.5 Y233 F5000
```

You'll also need to tweak the Z offset in `config.g`. I ended up with an offset of `5.70`. So the tool head appears to be about 0.7mm longer than stock with an E3D Nozzle X installed. Be careful and set the offsets correctly to avoid a crash.

# Happy Printing!
