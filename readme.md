# About

<a href="images/extruder-front.jpg"><img alt="Extruder Front" height="320" src="images/small/extruder-front.jpg"/></a>
<a href="images/extruder-left.jpg"><img alt="Extruder Left" height="320" src="images/small/extruder-left.jpg"/></a>
<a href="images/extruder-pair-back.jpg"><img alt="Extruder Pair Back" width="320" src="images/small/extruder-pair-back.jpg"/></a>
<a href="images/extruder-pair-left.jpg"><img alt="Extruder Pair Side" width="320" src="images/small/extruder-pair-left.jpg"/></a>

This is a tool designed for the E3D Tool Changer platform. It uses the Bondtech Mini Gear (BMG) drive parts and the Slice Engineering Mosquito for a compact and light weight (400g) direct drive extruder.

# Source

The project was designed in OnShape and you can access the released design here: [E3D Tool Changer - Bondtech Mini Gear (BMG)/Slice Mosquito Tool Head](https://cad.onshape.com/documents/296b560eee7721bd4ef989d0/w/90142d42ff99dde68f53c17c/e/d21c095bd78c720c7f814c17). 

The project is configured to allow forking and export of .stl and other formats. Work may be in progress, for the latest tested .stl files please use this github repo.

The STL files, this readme and these assembly instructions are maintained on [GitHub - Slice-Mosquito-Direct-Tool-Head](https://github.com/garethky/Slice-Mosquito-Direct-Tool-Head). You can also file an issue there.

## Why Build One?
* It's a geared direct drive extruder that can print faster and more precisely that the stock bowden tooling.
* The Mosquito hot end makes it very easy to swap nozzles. "Volcano" version of the Mosquito has the same nozzle hight so they can share wipers/brushes.
* It uses the stock dock pins in its stock location. No dock mods required.
* Light weight. Measured as 400g all up weight with tool plate.
* 40mm hot end fan and 5015 part cooling for quiet and effective cooling.
* Compact size, wont steal space from other tools or collide with the printer frame.
* Designed for manufacture on FDM printers. Most parts dont require supports and can print on 

## Project Status: Beta 2
This is the second release. Issues with the first release have been addressed, primarily around the part cooling nozzle design. This version also incorporates a 40mm fan on the hot end so you can use the silent Noctua fans.

## Required Parts, Printing & Assembly
[Assembly Instructions](assembly-instructions.md)

## Extruder Setup and Printing
[Extruder Setup & Printing](setup.md)

# Q and A

### Is this done, will there be changes?
Rev 2 is printing well for me now. I'm waiting for usage reports from others before making any more alterations.

### Will you adapt this design for the E3D V6?

The V6 mounts differently and the extruder would have to be split along the filament path to capture the mount. Thats a very big change and it wont be easy to maintain both versions. There is also the [Hemera](https://e3d-online.com/e3d-hemera-175-kit) which is a great value vs this design. You're free to fork the design if you like.

### How about Duet 3 Tool Board support?

I like the concept but the boards are kind of large. My worry with this is mostly about where to put it without making the whole package larger.

### Will you post this to Thingiverse/Prusa Printers/Other Platform

For the time being no. The audiance for this pretty narrow right now and for my workflow github is just nicer.

# Happy Printing!
