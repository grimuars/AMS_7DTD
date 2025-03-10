# Workbench Patches
## Fuel
Vanilla workstations are all hardcoded to accept the same fuels. IDC Core features patches that allow workbenches to only use a specific fuel. The following property can be added to custom workstations or appended to vanilla workstations to restrict the fuel usable by that workstation.   
``` xml
<property name="Fuels" value="resourceSnowBall,100"/>
```
The property takes a list in the form of `<item>, <fueltime>, <item>, <fueltime>, etc` and will take any number of fuels as long as there is a matching time to go with it.
