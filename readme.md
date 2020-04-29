# About 
This is a tool designed for the E3D Tool Changer platform. It uses the Bondtech Mini Gear (BMG) drive parts and the Slice Engineering Mosquito for a compact and light weight direct drive extruder. 

# Source
The project was designed in OnShape and you can get the source here:

[E3D Tool Changer - Bondtech Mini Gear (BMG)/Slice Mosquito Tool Head](https://cad.onshape.com/documents/296b560eee7721bd4ef989d0/w/77731089a76ed16562e3d253/e/d21c095bd78c720c7f814c17). The project is configured to allow forking and export of .stl and other formats. Work may be in progress, for the latest tested .stl files please use this github repo.
* STL files, this readme and these assembly instructions are maintained on [GitHub - Slice-Mosquito-Direct-Tool-Head](https://github.com/garethky/Slice-Mosquito-Direct-Tool-Head), you can also file an issue there.

This work is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)

## Goals
* Geared direct drive: can print faster and more precisely.
* Use the stock dock pins in its stock location. No dock mods required.
* Keep center of mass near the center of the kinematic coupling to limit wobble and print artifacts.
* Light weight. Measured as 400g with a 25mm stepper including tool changer plate.
* Easy to print with no required support material in PETG filament.

## Project Status: Beta
Currently this project is in Beta. Now is a good time to print an extruder and try it out for yourself. Before this release, several prototypes were printed and tested to failure. Improvements to the design have been made that should overcome these issues. Numerous print-ability tweaks have been made to eliminate the need for support material when printing. Print-ability, usability and general fit/finish should be fine for general use. I'm installing printing 4 on my tool changer so I can work on multi-material and multi-color printing.

## Required Parts, Printing & Assembly
See the [Assembly Instructions](assembly-instructions.md)

# Tool Changer / Duet Setup
## Slice Thermistor Setup with Duet
If using, the [RepRap Configurator](https://configtool.reprapfirmware.org/Heaters) has the settings you need, you can generate a config a pull the thermistor line out. Looks like this:

```
M305 S"T1" P1 T500000 B4723 C1.196220e-7 R4700 
```

## Tool Location
This tool sticks out further from the dock than the stock V6 tool. You'll need to edit `tpreN.g` and `tfreeN.g` to change the location where the tool is collected. Please use the calibration procedure [outlined by E3D](https://e3d-online.dozuki.com/Guide/10+-+Commissioning./104?lang=en) to work out the correct offsets for your printer. Expect your Y offset to be something like `239` to `240`.

## Z Offset
You'll also need to tweak the Z offset in `config.g`. I ended up with an offset of about `4.1` with an E3D Nozzle X installed. Be careful and set the offsets correctly to avoid a crash.

# Printing & Slicing Settings

##Max Acceleration##
This needs to be high enough that your extruder can reach your desired retract speed for the majority of your retract length. Retracts are generally the most demanding speed changes on an extruder axis. You can use the calculator here to build an intuitive sense for how that works: https://blog.prusaprinters.org/calculator/#speed

Suggested value: **5000mm/s^2**

That enough acceleration to reach 35mm/s in a 0.4mm retract and stay there for a about ~35% of the distance. If you do longer, slower retracts you might be able to go down on this a bit. 

Low extruder acceleration has several bad effect on print quality that you can see, including:
* Weak infill (extruder cannot accelerate fast enough)
* Over extrusion on solid layers (deceleration not fast enough leading to ooze)
* Lots of plastic clinging to the nozzle or extra plastic blobs on the part.
* Bad seams
* Print speed slows when pressure advance is turned on

If you are having these issues try raising the extruder acceleration even further.

## Max Instantaneous Acceleration ##
Also known as "Jerk", this is an exception to regular acceleration. If the change in speed required falls within this range the stepper will be commanded to do it instantly without breaking it up over multiple steps.

Values between 1mm/s and up to 3mm/s seems to work well for this extruder. Duet takes this in minutes so we must multiply by 60:

Suggested value: **90mm/min** (i.e. 1.5mm/s)

High jerk values can cause unnecessary wear on the extruder. You can hear this as clicking/clunking of the extruder gear train as it snaps in the opposite direction on a retract or de-retraction. I've seen profiles setting this as high as 8000 (133mm/s !!). Any value higher than the retract speed should, in theory, negate the acceleration setting. If you set acceleration high enough you wont need to set this very high at all.

## Expect to Print Hotter
You may need to raise the print temp by 5°C to 10°C over what you might have used with a V6. The most noticeable artifacts of low print temps is poor layer adhesion and gaps at seams.

I'm not sure if this is related to the cooling fan arrangement, the part cooling fan or the Mosquito's shorter melt zone.

## Set Retractions Shorter than a V6
Slice recommend using the nozzle diameter as the retraction ammount. 0.4mm nozzle  == 0.4mm retracts.

But what about more difficult filaments like PETG? Try starting with just double the nozzle diameter. If you still get stringing try reducing retraction speeds to 25mm/s. (my PETG sweet spot is 0.8mm, 25mm/s) Too much retraction distance can tear the filaments inside the hot zone and lead to bubbles. You will head a "popping" sounds when the bubble is extruded. If you get popping and voids in your prints, try reducing retract length.

## Pressure Advance
When you have dialed in all of the above variables its time to tune pressure advance with a test print. I like Marlin's [K-Factor test](https://marlinfw.org/tools/lin_advance/k-factor.html). You'll have to edit the .gcode for the Duet but its not hard once you have a slicer set up with custom GCode that you can copy from. A good range of values to test is is probably 0.01s to 0.1s.

Suggested value = **0.055s**

This was found in PETG with 20mm/s vs 80mm/s speeds. Tuen for your preferred material & print speeds.

# Q and A
## Will you adapt this design for the E3D V6?
The V6 mounts differently and the extruder would have to be split along the filament path to capture the mount. Thats a very big change and it wont be easy to maintain both versions. There is also the [Hemera](https://e3d-online.com/e3d-hemera-175-kit) which is a great value vs this design. You're free to fork the design if you like.

## Is this done, will there be changes?
Oh there are going to be changes... when I get time:
1. Prusa Labs has released their filament sensor as open source and inexpensive third party kits are available. This will enable automated filament loading and unloading and filament runout detection. The next major release will have the filament sensor integrated as an optional add-on.
2. I'm not satisfied with the way the filament enters the extruder. This release eliminated the push fit connector I was using. Bondtech's connector is inexpensive and is being evaluated. for now simply using no connector is fine and makes filament swaps easier.
3. The Cable Support that attaches the metal band and wiring loom is something I want improve and possible integrate into the motor plate. The extra part and fasteners dont seem to be beneficial. Cable routing in general isnt as clean as I wanted.

## How about Duet 3 Tool Board support?
I like the concept but the boards are kind of large. My worry with this is mostly about hwere to put it without making the whole package larger.

## That Mosquito fan is a menace
I noticed that too. Slice recommends running their fan at 70% (per https://www.sliceengineering.com/pages/documentation). Only the main Duet 2 board has PWM controlled ports for the hot end coolers to permit this. The Duet 3 expansion board has PWM fan ports. I'm upgrading to the Duet 3 and I'll be evaluating the noise at the 70% setting with 4 extruders. If thats too noisy, a mod to run a quieter fan would be something to consider. To have any benefit we would have to go up to the smallest Noctua fan.

# Happy Printing!
