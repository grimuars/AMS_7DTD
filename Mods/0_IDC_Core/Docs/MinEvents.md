# MinEvents
IDC Core features several event actions that can be called via buffs.

## SetWalkType
Allows for an entities walk type to be changed by buffs. 
 ```xml
<triggered_effect trigger="onSelfBuffUpdate" action="SetWalkType,IDCCore" value="<walk type>"/>
```

## AddChunkHeat
Allows for buffs to add chunk heat.
 ```xml
<triggered_effect trigger="onSelfBuffUpdate" action="AddChunkHeat,IDCCore" event_type="<type>" value="<value>"/>
```
Value can be any number between 0 and 100. Event type can be any of the following: Campfire, Forge, KillAnimal, Sound, Smell, Carcass, Torch. These values are not case sensitive. If event_type is not specified, the default type is Campfire.
