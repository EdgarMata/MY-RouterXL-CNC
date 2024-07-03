# How to use torch height probing with plasma cutting in Fusion360

## Things to do in Fusion360
* Select a plasma tool and adjust the kerf width to suite your machine.
* Make sure that the stock is the same thickness as the model, make sure no stock is added on top of the material.
* On all operations select Top Height as 'Stock Top' and enter the cutting head height for normal cutting (like 0.8mm).
* On all operations set the Pierce Clearance under Linking, must be greater than the cutting height (like 1.5mm).
* Under Passes | Compensation Type select 'In computer'.

## Things to do in the post options:
* Set 'Use Z touchoff probe routine' to Yes
* Set 'Plasma touch probe offset' to the difference between where the probe touches the material and where the probe triggers.
  * This is always in millimeters.
  * So if your probe triggers 5.3mm after the probe touches the material, enter 5.3, (always a positive number).
* Set 'Spindle on/off/ delay' to the desired Pierce delay in seconds. 

## Things you can adjust by editing the post:
* Open the .cps file in Notepad
* Search for 'USER ADJUST'
* You can change the probe distance and probe feedrate to suite your machine.
* Feedrate cannot be lower than 50mm/min, this is a GRBL internal limit.
