# Vehicle Patches
## Fuel
IDC Core features the ability to set a vehicle's fuel item. In vanilla, vehicles are forced to use gas as fuel. IDC Core allows that to be changed. A vehicles fuel item can be specified on its entry in `vehicles.xml`. This property will work on vanilla and modded vehicles. Vehicles without this property will follow vanilla behavior.

The below example will set the 4x4 truck to use small stones as fuel.
```xml
<config>
	<append xpath="/vehicles/vehicle[@name='vehicle4x4Truck']">
		<property name="fuelItem" value="resourceRockSmall" />
	</append>
</config>
```

## Drivable Terrain
IDC Core can allow vehicles to only drive on top of specific blocks. This can be used to create vehicles that only drive on roads, water, etc. Vehicles without this property will follow vanilla behavior. Block restrictions are specified via an XML property on the vehicle's `entityclasses.xml` entry. An example is provided below.
```xml
<config>
	<append xpath="/entityclasses/entity_class[@name='vehicleMinibike']">
		<property name="AllowedBlocks" value="block1,block2,block3"/>
	</append>
</config>
```
This patch will allow the minibike to only be drivable on blocks 1, 2, and 3. Any number of blocks can be defined as long as the list is comma separated.

## Damage Reduction
IDC Core allows for a property to be set on vehicles to reduce the amount of damage the vehicle takes. This property is a percentage multiplier to the damage taken.  The property is defined on a per vehicle basis. The below example will reduce the damage the minibike takes by 75%. 
```xml
<config>
	<append xpath="/entityclasses/entity_class[@name='vehicleMinibike']">
		<property name="DamageReduction" value="0.75"/>
	</append>
</config>
```