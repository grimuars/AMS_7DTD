# Passive Collector
A passive collector will generate resources at a randomly chosen interval between its min and max times. A passive collector is capable of taking modifiers that can change the block's behavior if those modifiers are present.

# Defining Output Items
A passive collector is capable of producing a variety of items. For the items to be parsed correctly, a block must have the following property for the parser to pick them up:  
```xml
<property name="HasItemConversions" value="true"/>
```

If multiple items are added to the output list, it will pick randomly from the list. An item can be defined as such: 

```xml
<item_conversion item="<item name>" lower_range="1" upper_range="10"/>
```

The item name must be the name of the item as defined in its xml entry. The lower range must be greater than 0 and the upper range must be less than the max stack size of the item. If the upper and lower range are the same number, then the collector will produce the number specified.
A block can have an infinite number of items in its item list, but the more items there are, the less of a chance a specific item is chosen. The list is not weighted.

# Modifiers
Modifiers are like tools in workstations. They are capable of changing various block properties. The following modifiers are currently available:

- Speed
  * Changes min and max production times by the percentage given. Positive values decrease production time. Negative values increase production time. Multiple speed modifiers can be defined on a block. The effect of multiple speed modifiers is multiplicative.
- Output Slots
  * Adds an additional number of container rows to the block. Only one output slot modifier can be added to a block.
- Replace Item
  *  A replace item modifier will replace one item in the output list with another. Multiple replace item modifiers can be defined on a specific item, but only the first modifier will take effect.
- Item Quantity
  * An item quantity modifier will change the specified item's output range.
- Heat Map
  * A heat map modifier can change the heat produced by the block.
- Rolls
  * A rolls modifier can change the number of rolls the block does when producing items.

# Defining Modifiers
Modifiers are defined on the block and parsed by a custom XML parser. In order for the parser to detect the properties on the block, the following property must be defined:
```xml
<property name="HasModifiers" value="true"/>
```
Blocks without this property will not have their modifiers read even if they have modifiers defined. 

The number of modifier slots must also be defined on the block.
```xml
<property name="NumModifiersSlots" value="1"/>
```
**Note:** The number of modifier slots is not the total number of modifiers. It is the count of the number of unique modifier items. If a modifier has multiple effects, it should only be counted once towards this number.

Defining a modifier is simple.
```xml
<modifier name="<item name>" effect="<modifier>" value="<value 1>" secondary="<value 2>" thirdValue="<value 3>"/>
```

The modifier name must be the item name that will be placed into the modifier slot. The effect must be modifier type from the list in the previous section. Values 1, 2, and 3 may not all be used depending on the modifier type selected. A modifier can have multiple effects. Each effect must be defined as a new property. Some examples of modifiers can be found below.

- Speed
   ```xml 
  <modifier name="<item name>" effect="Speed" value="-0.2"/> 
  ```
 - Output Slots
   ```xml
   <modifier name="<item name>" effect="OutputSlots" value="3"/>
   ```
- Replace Item
  ```xml 
  <modifier name="<item name>" effect="ReplaceItem" value="<item to be replaced>" secondary="<item to replace with>"/>
  ```
- Item Quantity
  ```xml 
  <modifier name="<item name>" effect="ItemQuantity" value="<item whose quantity to change>" secondary="<new lower bound>" thirdValue="<new upper bound>"/>
  ```
- Heat Map
  ```xml 
  <modifier name="<item name>" effect="HeatMapModifier" value="<heat map strength mult>" secondary="<heat map time mult>" thirdValue="<heat map frequency mult>"/>
  ```
- Rolls
  ```xml 
  <modifier name="<item name>" effect="RollsModifier" value="<new rolls number>"/>
  ```
# Container Size
A passive collector's default container size is defined via XML. The following properties should be defined on the block. If these properties are not present, default values will be used.
```xml
<property name="ContColumns" value="3"/>
```
```xml
<property name="ContRows" value="1"/>
```

# Fuel
Passive collectors can also optionally require fuel. Fuel can either be an item with durability or a stackable item. If an item with durability is used, one durability will be consumed per operation of the passive collector. If a stackable item is used, one item will be consumed per operation. Fuel can be defined as follows:
```xml
<property name="FuelItem" value="<item name>"/>
```

# Sky Access
As of V2.0.2, passive collectors can disable their sky access requirement. The following property will disable the sky access requirement for the passive collector. Passive collector blocks without this property, or with the property set to true, will require sky access to function.
```xml
<property name="NeedsSkyAccess" value="false"/>
```
# Rolls
Passive collectors will roll X number of times when producing an item. This means the collector can produce items X number of times when its timer runs out. The default number of rolls is 1 however this value is configurable.
```xml
<property name="NumRolls" value="<number of rolls>"/>
```
A rolls value of 3 will cause the collector to produce items 3 times when its timer runs out.

# Further Examples
I'm sure all this information may be confusing. To see the passive collector in action, you can see some mods using it below.
[Advanced Dew Collector](https://www.nexusmods.com/7daystodie/mods/3150?tab=description&BH=0)  
[IDC Animal Snare](https://www.nexusmods.com/7daystodie/mods/3343/?tab=description)
[IDC Beehives](https://www.nexusmods.com/7daystodie/mods/3419/?tab=description)
