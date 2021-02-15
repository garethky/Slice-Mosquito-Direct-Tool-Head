# Extruder Setup and Tuning

## Duet Configuration

### Tool Clearance

This tool has a motor that sticks out over the tool changer head and interferes with the stock X-Carriage Cable Bracket. A remix of that part is included as a drop in replacement for the stock part.

### Slice Thermistor Setup with Duet

If using, the [RepRap Configurator](https://configtool.reprapfirmware.org/Heaters) has the settings you need, you can generate a config and pull the thermistor line out. Looks like this:

```
M305 S"T1" P1 T500000 B4723 C1.196220e-7 R4700 
```

### Tool Location Adjustments

This tool sticks out further from the dock than the stock V6 tool. You'll need to edit `tpreN.g` and `tfreeN.g` to change the location where the tool is collected. Please use the calibration procedure [outlined by E3D](https://e3d-online.dozuki.com/Guide/10+-+Commissioning./104?lang=en) to work out the correct offsets for your printer.

### Z Offset

You'll also need to update the Z offset in `config.g`. Be careful and set the offsets correctly to avoid a crash.

## Printing & Slicing
I am by no means an expert in 3D printer tuning. One of the big learning experiences for me on this project was just how much these settings impact print quality. For many weeks I though I had a problem with the extruder design but it ended up being largely down badly selected Acceleration and Jerk values. Below is how I now think about tuning these parameters:

### Max E-Axis Acceleration

This needs to be high enough that your extruder can reach your desired retract speed for the majority of your retract length. Retracts are generally the most demanding speed changes on an extruder axis. You can use the calculator here to build an intuitive sense for how that works: https://blog.prusaprinters.org/calculator/#speed

Suggested value: **3000mm/s^2**

The default in Marlin is 10000K mm/s^2, more than double the above value, so I'm probably being conservative here.

### Max E-Axis Instantaneous Acceleration / Jerk

This is an exception to regular acceleration. If the change in speed required falls within this range the stepper will be commanded to do it instantly without breaking it up over multiple steps.

Values between 1mm/s and 5mm/s seem to be a good place to start. Duet takes this in mm/minute so we must multiply by 60:

Suggested value: **90mm/min** (i.e. 1.5mm/s)

Very high jerk values can cause unnecessary wear on the extruder. You can hear this as clicking/clunking of the extruder gear train as it snaps in the opposite direction on a retract or de-retraction. Conversely, if the value is too low printing will slow down when Pressure Advance is used. If you see slowing you will need to raise the Jerk value (and possibly acceleration) and re-tune pressure advance. A jerk value that sounds harsh without pressure advance may end up being too low with it on. For reference, Marlin defaults this to 300mm/min (5mm/s). If you find you need values much higher than this, raise the acceleration value instead.

### Set Retractions to the Nozzle Diameter
Slice Engineering recommends using the nozzle diameter as the retraction amount. 0.4mm nozzle == 0.4mm retracts. Bondtech recommends running retractions at 35mm/sec. I've found these settings print well.

But what about oozy filaments like PETG? I actually dont have a problem printing PETG with these settings. I have found that the Mosquito is more vulnerable to moisture in the filament which manifests as weak infill and stringing. Dry your filament before chasing retraction settings.

### Pressure Advance Tuning
When you have dialed in all of the above variables its time to tune pressure advance with a test print. I like Marlin's [K-Factor test](https://marlinfw.org/tools/lin_advance/k-factor.html). You'll have to edit the .gcode for the Duet but its not hard once you have a slicer set up with custom GCode that you can copy from. A good range of values to test on this extruder is `0.01s` to `0.2s`in `0.01s` increments. You're value will depend on your print setting, speeds and the ooziness of your filament. The optimal value on my machine, in PETG, ended up being **0.03s**.
