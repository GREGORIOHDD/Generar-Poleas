# OpenSCAD_Pulley_Library
### OpenSCAD library to create multiple types of pulleys from belt sizes in 3D

Thingiverse Thing: [2105020](http://www.thingiverse.com/thing:2105020)

*v.01 - February 12, 2017*

+ linkages.scad: 3D Pulleys
+ `step` and `customstep` up to 6 pulleys

Add to your library folder in OpenSCAD and use the include function to begin using these modules.

```scad
include <pulleys.scad>
```    

[OpenSCAD Libraries (Manual)](https://en.wikibooks.org/wiki/OpenSCAD_User_Manual/Libraries "OpenSCAD Libraries")

Default units are inches.

### Pulley Modules

![alt text](https://github.com/machineree/OpenSCAD_Pulley_Library/blob/master/pics/pulleyex1.png?raw=true "Pulleys!")

1. `module pulley(type="4L", definedD, arborD, key=.125, res=60, padding=true, screw=false)`

  + **type:** type of belt: 2L, 3L, 4L, 5L, A, B, C, D, E, 3V, 5V, 8V
  + **definedD:** desired outer diameter of the pulley
  + **arbor:** arbor or spindle diameter, through the pulley
  + **key:** square key slot, default is 1/8"
  + **res:** resolution of the circles, default is $fn=60
  + **padding:** adds a layer on either side of the pulley dependant upon the belt width
  + **screw:** places a set screw hole to be tapped that is lined up with the key to be locked on the arbor/spindle
  
2. `module custompulley(beltB, beltH, beltangle, definedD, arborD, key=.125, res=60, padding=true, screw=false)`

  + **beltB:** width of the belt
  + **beltH:** height of the belt
  + **beltangle:** angle of the belt
  + **definedD:** desired outer diameter of the pulley
  + **arbor:** arbor or spindle diameter, through the pulley
  + **key:** square key slot, default is 1/8"
  + **res:** resolution of the circles, default is $fn=60
  + **padding:** adds a layer on either side of the pulley dependant upon the belt width
  + **screw:** places a set screw hole to be tapped that is lined up with the key to be locked on the arbor/spindle
  
3. `module stepN(type="4L", dia1,dia2,...,diaN, arborD, key=.125, res=60, padding=true, screw=false)`

  + **type:** type of belt: 2L, 3L, 4L, 5L, A, B, C, D, E, 3V, 5V, 8V
  + **diaN:** desired outer diameter of each pulley, enter each diameter in order
  + **arbor:** arbor or spindle diameter, through the pulley
  + **key:** square key slot, default is 1/8"
  + **res:** resolution of the circles, default is $fn=60
  + **padding:** adds a layer on either side of the pulley dependant upon the belt width
  + **screw:** automatically places a set screw on the second pulley 
  
3. `module customstepN(beltB, beltH, beltangle, dia1,dia2,...,diaN, arborD, key=.125, res=60, padding=true, screw=false)`

  + **beltB:** width of the belt
  + **beltH:** height of the belt
  + **beltangle:** angle of the belt
  + **diaN:** desired outer diameter of each pulley, enter each diameter in order
  + **arbor:** arbor or spindle diameter, through the pulley
  + **key:** square key slot, default is 1/8"
  + **res:** resolution of the circles, default is $fn=60
  + **padding:** adds a layer on either side of the pulley dependant upon the belt width
  + **screw:** automatically places a set screw on the second pulley 

### Naming Strategy:

pulley

custompulley

step*N*

customstep*N*

### Examples!

Single Pulley - 5L Belt, 6" Outer Diameter, 5/8" Center Bore

This displays the simplicity of the pulley library to make pulleys quickly.

```openscad
include <pulleys.scad>

pulley("5L", 6, 5/8);
```
![alt text](https://github.com/machineree/OpenSCAD_Pulley_Library/blob/master/pics/ex1.png?raw=true "Simple Example")

![alt text](https://github.com/machineree/OpenSCAD_Pulley_Library/blob/master/pics/ex1-1.png?raw=true "Simple Example")

Single Pulley - 4L Belt, 4" Outer Diameter, 1/2" Center Bore, Keyway of .2", $fn=100, .218" Set Screw

```openscad
include <pulleys.scad>

pulley("4L", 4, 1/2, key=.2,, res=100, screw=true);
```
![alt text](https://github.com/machineree/OpenSCAD_Pulley_Library/blob/master/pics/ex2.png?raw=true "Simple Example")

![alt text](https://github.com/machineree/OpenSCAD_Pulley_Library/blob/master/pics/ex2-1.png?raw=true "Simple Example")

![alt text](https://github.com/machineree/OpenSCAD_Pulley_Library/blob/master/pics/ex2-2.png?raw=true "Simple Example")

Single Pulley - Custom Belt(.5125" width/.475 height/34 deg. angle), 5" OUter Diameter, 5/8" Center Bore

Added Animation to spin pulley to see all sides:

```openscasd
include <pulleys.scad>

rotate([360*$t,360*$t,90])
custompulley(.5125,.475, 34, 5, 5/8);
```

![alt text](https://github.com/machineree/OpenSCAD_Pulley_Library/blob/master/pics/ex3.gif?raw=true "Custom Example")

Output of help within OpenSCAD console:

```openscad
include <pulleys.scad>

pulleyhelp();
```

![alt text](https://github.com/machineree/OpenSCAD_Pulley_Library/blob/master/pics/pulleyhelp.png?raw=true "pulleyhelp")
