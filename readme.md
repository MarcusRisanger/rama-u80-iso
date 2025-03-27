# ISO Conversion: Rama Works U80-A SEQ2

This repo contains resources you need for converting your U80-A to ISO layout. I really loved this keyboard when I saw it, but the lack of ISO compatibility threw me off. 

After some deliberation I decided to purchase a board outright from a friendly user from [r/mechanicalkeyboards](https://www.reddit.com/r/MechanicalKeyboards/) and just assume I would be able to get the conversion working.

Now that I have gotten everything up and running (and confirming that it works!) I want to share these resources free of charge for other ISO-ers out there who likes a properly chonky keyboard.

## Resources

In the repo you will find everything you need to convert:

* Plate file (DXF) format
* PCB files
* PCB firmware

Apart from this, you have to make a tiny cut to the MUTE mount when doing final assembly. 

### Plate

The plate file is derived from the official U80 plate which was released by Rama Works, but only supports ANSI tsangan. Making the changes was pretty straightforward using the generated file from [Keyboard Layout Editor](https://www.keyboard-layout-editor.com/) as a "stencil" in a CAD software.

I had the plate cut out of brass by [LaserBoost.com](https://www.laserboost.com/), and this worked fine. However, the laser cutting was very precise, so I had to use a metal file to file down some of the edges so they didn't touch the inside of the chassis during mounting. I suppose this has something to do with "kerf", which is nearly nonexistent in water jetting but can make a difference in other types of plate manufacturing.

Note: The thickness should be 1 millimeter to match the original plate. If in doubt, use your original ANSI plate to measure.

### PCB

Since I didn't want to learn a bunch of electronics CAD just for this project, I hired [Ahsan Awan](https://www.fiverr.com/pcbdesign_engr) from fiverr to do the actual PCB design based on my requirements.

The PCB is specified from 3 files:

* `Gerber File.zip`: for the actual PCB layout, routing etc.
* `Pickplace CPL.xlsx`: specifies the components, location, orientation etc.
* `Part List BOM.xlsx`: translates components from Pickplace file to JLCPCB part list

Since I used [JLCPCB]() for manufacturing, the parts list is made for that purpose. The PCBs were quite cheap and were shipped in no time at all.

**NOTE**: The parts numbers may be out of date by now, so there may be some translation to be made. I'm sure JLCPCB support can help in that case.

**NOTE 2**: If you want to use a different PCB manufacturer, you have to modify the part list according to the specifications of that vendor. Good luck!

**NOTE 3**: You have to get Kailh hotswap sockets (from e.g. Aliexpress) yourself and have them soldered on manually. If you have a friend with a solder iron, buy them a bottle of wine (like I did) as payment (instruct them to enjoy the wine AFTER soldering....)


### PCB Firmware

Based on the file package I received with the PCB files, I was able to sit down and code the required QMK firmware for the PCB. This comes in the form of a HEX file, and I leave it up to the eager reader to figure out how to use this together with the QMK suite for flashing your PCB.

To enter bootload mode, hold down ESC while you plug in your keyboard. Or use the reset button on the back of the PCB.

If you wish to make your own firmware, you can use my `qmk-config.zip` as a starting point.

**NOTE**: The firmware ***is*** VIA compatible for easy remapping of keys.

