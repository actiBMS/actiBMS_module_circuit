# diyBMSv5_module_circuit
Version 5 of the diyBMS, this repository contains the pcb project

THIS IS A WIP VERSION, SO LAST MINUTE CHANGES COULD BE DONE!

Do it yourself battery management system for Lithium ion battery packs/cells

If you are looking for version 4 of this project take a look here https://github.com/stuartpittaway/diyBMSv4

# TRAVIS-CI
TODO

# Videos on how to use and build

https://www.youtube.com/stuartpittaway


# WARNING

This is a DIY product/solution so don’t use this for safety critical systems or in any situation where there could be a risk to life.  

There is no warranty, it may not work as expected or at all.

The use of this project is done so entirely at your own risk.  It may involve electrical voltages which could kill - if in doubt, seek help.

The use of this project may not be compliant with local laws or regulations - if in doubt, seek help.


# License

This work is licensed under a Creative Commons Attribution-NonCommercial-ShareAlike 2.0 UK: England & Wales License.

https://creativecommons.org/licenses/by-nc-sa/2.0/uk/

You are free to:
* Share — copy and redistribute the material in any medium or format
* Adapt — remix, transform, and build upon the material
The licensor cannot revoke these freedoms as long as you follow the license terms.

Under the following terms:
* Attribution — You must give appropriate credit, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.
* Non-Commercial — You may not use the material for commercial purposes.
* ShareAlike — If you remix, transform, or build upon the material, you must distribute your contributions under the same license as the original.
* No additional restrictions — You may not apply legal terms or technological measures that legally restrict others from doing anything the license permits.


Notices:
You do not have to comply with the license for elements of the material in the public domain or where your use is permitted by an applicable exception or limitation.

No warranties are given. The license may not give you all of the permissions necessary for your intended use. For example, other rights such as publicity, privacy, or moral rights may limit how you use the material.

Full license available https://github.com/diyBMS/diyBMSv5_module_circuit/blob/master/LICENSE


# Problem

A DIY Powerwall is the DIY construction of a pack of battery cells to create an energy store which can be used via inverters to power electrical items in the home. Generally cells are salvaged/second hand, and typically use Lithium 18650 cells.

Lithium batteries need to be kept at the same voltage level across a parallel pack. This is done by balancing each cell in the pack to raise or lower its voltage to match the others.

Existing balancing solutions are available in the market place, but at a relatively high cost compared to the cost of the battery bank, so this project is to design a low-cost, simple featured BMS/balancer.

# How it works

Each cell in a battery pack has a monitoring module. Each module have a micro on it that manage all the important task to keep the pack safe. This uses AVR ATTINY841 linked together by optoisolated serial ports for communication.

The controller enable a BYPASS resistor, parallel to the CELL, to dump additional power during charge to keep the pack balanced. Another solution is to enable the Active Balancing, this feature is based on the ETA3000 chip. It is able to move power between adiacent cells. A more detailed teory of operation about this inductive converter chip can be read here:
 - https://www.beyondlogic.org/review-li-ion-lipo-lifepo4-lithium-battery-active-equalizer-balancer-energy-transfer-board/
 - https://circuitdigest.com/article/cell-balancing-techniques-and-how-to-use-them

ATTINY841 provides:
* Internal temperature monitoring
* External temperature monitoring
* Autonomous PASSIVE cell voltage balancing
* Autonomous ACTIVE cell voltage balancing

# How as v5 improved over v4?

* Highter discharge current
* Better thermal design for the passive balancing tecnique
* Inductive Active Balancing - Low heat production, less energy loss from your PV


# Design Goals

* Build upon my existing skill set and knowledge. 
* Building something that others can contribute to using regular standard libraries and off the shelf components.
* Build something that is inheriently safe and easy to use
* Document it to inspire other people
