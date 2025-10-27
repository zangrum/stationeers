# Atmospherics
There are 2 types of atmospherics platforms I have designed.  One for gaseous elements that turn to Fluids at 27 degrees, high pressure,  and One for ones that stay Gas at high pressure.   N20 and Pollutants should use the Fluid builds.  The others can use the gas build.  

## Basic Design
The basic design has one waste pipe that all the filters feed off of.  It uses a set of IC chips to turn the filter and accompanying pumps to inactive/off if there is no air of the filterable type.  There is a set of Ice Crusher, Gas Canister Storage and Portable Container Storage that will feed the waste pipe.  It will also have one way pipes with a pump into it from other systems.

```mermaid
flowchart TD
ice_crusher[Ice Crusher]
ice_crusher-->wastePipe
wastePipe[Waste Pipe]    
wastePipe-->liquidDrainWaste["Passive Liquid Drain"]
wastePipe-->Pol
subgraph Pol["Pollutants"]
    condensationValvePol["Condensation Valve"]
    liquidStoragePol["Insulated Liquid Tank"]
    expansionValvePol["Expansion Valve"]
    powerControllerPol["APU "]
    pipeHeaterPol["Pipe Heater"]
    filterPol["Filter"]
    wastePipePol(("Waste Pipe"))
    storagePol["Insulated Tank"]
    wasteRegulatorPol["Waste Back Pressure Regulator"]
    volumePumpPol["Volume Pump"]
    insulatedPipe["Insulated Pipe"]
    usagePipePol["Usage"]
    oneWayPipePol["One Way Pipe"]
    wastePipePol-->filterPol
    insulatedPipe-->condensationValvePol-->liquidStoragePol-->expansionValvePol-->insulatedPipe
    insulatedPipe-->oneWayPipePol-->usagePipePol
    insulatedPipe-->storagePol
    filterPol-->volumePumpPol-->pipeHeaterPol-->insulatedPipe
    filterPol-->wasteRegulatorPol-->wastePipePol
    

end
wastePipe-->O2
subgraph O2["Oxygen"]
    liquidDrainO2["Passive Liquid Drain"]
    pipeHeaterO2["Pipe Heater"]
    powerControllerO2["APU (O2)"]
    ledDisplayMols["Small Led (Mols)"]
    consoleDisplayPress["Console (Gas/Pressure)"]
    filterO2["Filter (O2)"]
    storageO2["Insulated Tank (O2)"]
    volumePumpO2["Volume Pump (O2)"]
    wasteRegulatorO2["Waste Back Pressure Regulator (O2)"]
    wastePipeO2(("Waste Pipe"))
    oneWayPipeO2["One Way Pipe"]
    usagePipeO2["Usage"]    
    wastePipeO2-->filterO2
    volumePumpO2-->liquidDrainO2
    pipeHeaterO2-->oneWayPipeO2-->usagePipeO2
    filterO2-->volumePumpO2-->pipeHeaterO2-->storageO2
    filterO2-->wasteRegulatorO2-->wastePipeO2
    controlWires["Wiring"]
    filterO2-.->controlWires
    controlWires-.->volumePumpO2
    controlWires-.->pipeHeaterO2
    controlWires-.->wasteRegulatorO2
    controlWires-.->ledDisplayMols
    controlWires-.->consoleDisplayPress
    controlWires-.->storageO2
    controlWires-.->light["Flashing Light"]
    powerControllerO2-.->controlWires
end
```

## Gaseous Element Filter
Build a 1 by 6 Frame section. L: Liquid Storage S: Storage Tank, P: Piping, F: Filtration unit, W: Waste Pipe, Input on ground and Gas Output On Ceiling, C: Control Wall, [#]: Walkway you have already built connected to main building
```
[L] [S] [P] [F] [W] [C]|[#] [#]
```
*Ingots: 32 Iron, 74 Copper, 16 Gold, 71 Silicon, 77 Steel, 5 Electrum, 5 Solder*
* 6X Steel Frames *(2g Steel each)*
  * 12X Steel Sheets *(0.5 Steel each)*
* 3X Composite Walls
* Spray Paint *(1g Iron)*

* 40X Insulated Pipes *(1g Silicon, 1g Steel)*
* Pressure Regulator *(5 Iron, 2 Copper, 1 Gold)*
* Kit (Tank Insulated) *(5 Copper, Silicon 30, Steel 20)*
* Kit (Atmospherics) *(10g Iron, 20g Copper, 5g Gold)*
  * 2X Kit (Pipe) *(1 Iron)*
  * 2X Coil *(1 Copper)*
* Kit (Volume Pump) *(5g Iron, 3g Copper, 2g Gold)*
* Kit(Liquid Drain) *(5g Iron, 2g Copper)*
* Pipe Heater *(3g Copper, 3g Gold, 2g Steel)*

* IC10 Chip *(10 Gold, 4 Steel, 5 Electrum, 2 Solder)*
* 2X Console *(2g Iron, 5g Copper, 3g Gold)*
  * 2X Glass Sheet *(2 Silicon)*
  * Circuit Board (Gas Display) *(	1g Iron, 5g Copper, 5g Gold)*
* Power Controller *(5g Iron, 2g Copper, 3g Solder)*
* Battery Cell (Large) *(10g Copper, 5g Gold, 5g Steel)*
* Kit (Flashing Light) *(1g Iron, 2g Copper, 1g Silicon)*
* 2X Console *(2g Iron, 5g Copper, 3g Gold)*
  * 2X Glass Sheet *(2 Silicon)*
  * 2X Circuit Board (Gas Display) *(	1g Iron, 5g Copper, 5g Gold)*
* 50X Coil *(25 Copper)*