# CVTnithm

CVTnithm is a cable adapter in PCB form. That's about it!

Thanks to [@48productions](https://github.com/48productions) who made a guide on how to make all the necessary wiring and made me realize:

* Digikey doesn't sell the crimpable version of the connector
* I'm not buying a single part from JST directly
* also i don't want to buy a specialty crimper for molex pins (_except i kinda had to for handling ac power lmao_)
* also i'm lazy, but not lazy enough to make a pcb

## I'm sorry I didn't have a creative name for this project

To build this, you will need the following components:

* For the serial connections:
  * (1) [JST B22B-XADSS-N](https://www.digikey.com/en/products/detail/jst-sales-america-inc/B22B-XADSS-N-LF-SN/1300311)
  * (3) 2x5 IDC box headers, such as [SBH11-PBPC-D05-ST-BK](https://www.digikey.com/en/products/detail/sullins-connector-solutions/SBH11-PBPC-D05-ST-BK/1990062)
* For the power connections:
  * (1) [Molex Mini-Fit Jr. 5556](https://www.digikey.com/en/products/detail/molex/0039310140/2405381)
  * (2) PC 4-pin power connectors, such as [TE MATE-N-LOK 350211-1](https://www.digikey.com/en/products/detail/te-connectivity-amp-connectors/350211-1/30127)
    * NOTE: This connector works, but it is a _royal pain_ to disconnect the cable once it's plugged in.
* A CVTnithm PCB. Two options are provided:
  * The `alls` folder contains the PCB files used for an ALLS, such as an ALLS UX.
  * The `nu-alls` folder contains the PCB files for a Nu1.1-ALLS conversion.

Connecting this board internally requires the following:

* (3) 2x5 IDC cables, such as [these on Amazon](https://www.amazon.com/dp/B07FZWWGY3). The cables should be a straight connection without any twists or other modification. 

Solder each of these connectors in their respective places; each connector has a unique footprint so it should be fairly obvious what connectors need to go where. Be mindful of orientation!

## So I soldered this, now what?

* On an ALLS, remove the serial brackets by undoing the two PCI bracket screws, unplugging them from the motherboard in the process.
* Locate a suitable set of power cables.
  * In an ALLS, locate the collection of unused power supply cables. Undo this bundle and find a cable containing two PC 4-pin power connectors and a floppy drive connector.
  * In a Nu1.1-ALLS conversion, this will vary wildly depending on the power supply used. You will need two PC 4-pin power connectors, from one or two cables.
* Note the `COM_` number on each of the serial ports on the motherboard. Plug one IDC cable into each of the serial ports. Plug the other end into the CVTnithm PCB into its respective `COM_` port.
* Plug in the two PC 4-pin power connectors.

## How do I mount the ALLS PCB?

Print the two 3MF files in the `alls` folder in the orientations provided. The bottom bracket requires support material, and it's recommended to disable support for bridges as a small tool (like a dental pick) will be needed to clean out some of the support material otherwise. If you cannot disable support for bridges (due to slicer or printer limitations), you may try printing with the part upside-down as this will allow you to more easily clean out the support material.

With the rear of the ALLS facing you (herein described as the "front"), install everything as follows:

* Insert the bottom bracket into the two empty PCI slots from the _front_. The flat side should be facing you, with the `U` shape upward.
* Slide the bottom bracket as far down as you can. The metal of the PCI bracket should slide into a notch in the print.
* Looking at the ALLS from the top, fit the CVTnithm PCB into the notch in the bottom bracket. The CVTnithm board will be installed _inside_ the ALLS, with the IDC connectors facing downward.
* Place the top bracket over the CVTnithm PCB so the flat side is facing you, with the screw hole towards you. Reinstall the two PCI screws, making sure the CVTnithm PCB is retained by the bracket.

## How do I mount the Nu1.1-ALLS PCB?

Install the CVTnithm PCB where the AMEX PCB was previously installed with four screws. Text should be upright with the serial and DC output connectors facing outward.