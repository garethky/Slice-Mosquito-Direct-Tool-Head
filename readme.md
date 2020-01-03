
## Goals
* Geared direct drive - smaller stepper means lighter weight tool head which can print faster.
* Use the stock dock in its stock location
* Keep the nozzle location as close as possible to the stock location to enable sharing of wipers and preserve print volume.
* Keep mass near the center of the kenematic coupling to limit wobble and print artifacts.

## Projust Status: Prototype
Currently this project is a prototype. Several things are untested or need to be evaluated, including:
* The cooling fan location, orientation and the fan shroud design
* The Front Frame gets very close to the heat block. More testing is needed to make sure its safe from melting.

## Hardware Required
* Mosquito Hot End (if you go to buy one, not that the cooling fan, thermistor and heater carterige are not included). It does come with the 2.5mm screws you will need to mout it.
* All geared parts from the Bondtech BMG, they can be bought as acessories to save money
    * Bondtech Gear Set
    * Reduction Shaft
    * Spur Gear for the stepper
    * 2 Bearings
    * Idler shaft
* A Nema 17 packcake stepper that is at least 25mm long (most slimline or pancake steppers fit this description. (e.g. https://www.printedsolid.com/collections/ldo-motors/products/ldo-nema-17-motor-pancake-ldo-42sth25-1404?variant=21076331987029))
* M3 Socket Head cap Screws:
    * 2 x 30mm
    * 8 x 10mm
* M3 Hex Drive Flat Head Screws
    * 5 x 5mm
* M2.5 Socket Head cap Screws
* 2 x M2.5 x 5.5mm brass inserts, such as these: https://www.amazon.com/dp/B07NBPGTY2
* 1 x M3 x 5mm brass threaded insert, such as these: https://www.amazon.com/dp/B07NBRDHFN
* 1 x PC4-M10 Fitting
* A ???mm stepper cable
* Spring TK mm long by TK mm wide

## Printing The Parts
Every parts has a a face that was designed to print down on the print bed to help eliminate the need for supports. A couple of spots require some bridging and could be improved.

In addition to these parts you will need the right had version of the dock

I suggest using these settings:

* 4 perimeters - The front frame that holds up the Mosquito, in particular, needs the extra wall thickness to not flex
* 20% Grid Inflill

### Fan Shroud Special Notes
* Use ASA or ABS
* Fan Shoud requires supports under the two mounting legs. You can use support enrorcers in your slicer to limit the anout of suppor that gets gernated.

# Assembly
1. The stepper shaft needs to be cut so that it is at most TK mm long.
1. Install the 2.5mm threaded inserts in the Front Frame. Insert a piece of PTFE tubing into the filament path to support area while installing the inserts. there isnt much plastic there and we dont want to melt and deform the walls.
1. Install the M3 brass insert for the tension mechanisim
1. Make small length of PTFE tubing (~10mm) with a ^ on one end. 
1. Install the Mosquito into the front frame with the M2.5 x 5mm bolts included with the Mosquito kit. Make sure the heater cartrige faces the front (should be the face that was down when the part was printed)
1. 

1. Attach the spur gear to the stepper shaft, space between the gack of the gear and the shaft is TK mm.
1. Install a bearing into the Stepper Frame and install the reduction shaft
1. Mount the Receiver Frame to the Stepper frame with 2 x M3 x 10mm screws.
1. Mount the stepper to the stepper frame with 1 x M3 x TK mm bolt in the top right corner
1. Install the Mid Frame over the Stepper frame with 1  x M3 x TK mm bolt
1. Install the Bondtech Drive gear onto the reduction shaft but dont tighten it down yet
1. Temporarily add the bearing onto the shaft and put the Front Frame onto the assembly.
1. Use a piece of filament to 


1. Install the long shaft in the base of the Idler Arm
1. Install the Bondtech Idler on the short shaft and insert into the idler arm

