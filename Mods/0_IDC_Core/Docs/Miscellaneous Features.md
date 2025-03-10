# Miscellaneous Features
IDC Core features many smaller features that don't need their own wiki pages. All features can be configured in the config file `IDCCore\config\blocks.xml`.

## Trader Talk Icons
Trader talk icons are the yellow icons that appear when you get close to a trader. Sometimes those icons can be annoying. IDC Core allows those icons to be disabled. The property `NoTraderIcons` will fully disable the trader talk icons. The property `NoTraderIconsNight` will prevent those icons from appearing if the trader is currently closed. Only one option can be enabled at a time. By default, the night icons option is enabled.
```xml
<property class="TraderIconsConfig">
  <property name="NoTraderIcons" value="false"/>
  <property name="NoTraderIconsNight" value="true"/>
</property>
```

## No Zombie Spawns in Landclaims
By default, landclaims don't prevent zombies from spawning inside them. IDC Core has the ability to fix that. With this feature enabled, zombies cannot spawn inside landclaims for any reason. This feature is enabled by default however if you'd like to turn it off, the following property should be changed.
```xml
<property name="PreventZombiesInLandclaims" value="true"/>
```

## Multi Screamers
Tired of only one screamer spawning when the heat level for a chunk reaches 100? IDC Core can fix that. With the multi screamer functionality enabled, there is a chance that multiple screamers will spawn. The options for this feature are configurable. `MultiScreamerChance` dictates the chance multiple screamers are spawned. This value should be between 0 and 1. `MultiScreamerBounds` dictates how many screamers can be spawned. The first number is the lower bound, and the second number is the upper bound. A random number will be chosen between the two bounds. This feature is disabled by default.
```xml
<property class="ScreamerOptions">
  <property name="MultiScreamerEnabled" value="false"/>
  <property name="MultiScreamerChance" value="0.5"/>
  <property name="MultiScreamerBounds" value="2,4"/>
</property>
```

## Crop Trampling
Zombies don't trample crops in vanilla. IDC Core fixes that as well as offering multiple options to configure this feature.
```xml
<property class="PlantOptions">
  <property name="ZombiesTrampleCrops" value="true"/>
  <property name="AnimalsTrampleCrops" value="false"/>
  <property name="PlayersTrampleCrops" value="false"/>
  <property name="CropTrampleTag" value="cropTrample"/>
</property>
```
You must also add the tag defined in `CropTrampleTag` to any plants/crops you want to be trampled by the above settings.