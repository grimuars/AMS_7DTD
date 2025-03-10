# Gamestaged Biome Spawns
IDC Core allows for the biome spawns in the game (the zombies that spawn and wander the world) to be controlled by the player's gamestage. This allows the world to become more difficult as the player and time, progresses.
 This feature is disabled by default and can be enabled in the `IDCCore\Config\blocks.xml` file. This feature is also customizable via the use of entitygroups and spawners. A default setup for this feature is provided and can be used as a reference.

# Customizing Biome Spawns
There are two files you will need to modify to customize the biome spawns. The first is `gamestages.xml`. This file will control the gamestage values that are used to determine the spawner to use when spawning zombies. The spawner names MUST be the values shown below. All biome names do not need to be present. Biomes without a spawner entry will default to vanilla behavior.

Any number of gamestages can be defined. The number of gamestages defined per biome does not have to be the same.
## gamestages.xml
```xml
<config>
	<append xpath="/gamestages">
		<spawner name="pine_forest">
			<gamestage stage="1">
				<spawn group="pine_forest_GS1" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="50">
				<spawn group="pine_forest_GS50" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="100">
				<spawn group="pine_forest_GS100" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="150">
				<spawn group="pine_forest_GS150" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="200">
				<spawn group="pine_forest_GS200" num="1" maxAlive="1" duration="1"/>
			</gamestage>
		</spawner>
		<spawner name="desert">
			<gamestage stage="1">
				<spawn group="desert_GS1" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="50">
				<spawn group="desert_GS50" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="100">
				<spawn group="desert_GS100" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="150">
				<spawn group="desert_GS150" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="200">
				<spawn group="desert_GS200" num="1" maxAlive="1" duration="1"/>
			</gamestage>
		</spawner>
		<spawner name="snow">
			<gamestage stage="1">
				<spawn group="snow_GS1" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="50">
				<spawn group="snow_GS50" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="100">
				<spawn group="snow_GS100" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="150">
				<spawn group="snow_GS150" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="200">
				<spawn group="snow_GS200" num="1" maxAlive="1" duration="1"/>
			</gamestage>
		</spawner>
		<spawner name="wasteland">
			<gamestage stage="1">
				<spawn group="wasteland_GS1" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="50">
				<spawn group="wasteland_GS50" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="100">
				<spawn group="wasteland_GS100" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="150">
				<spawn group="wasteland_GS150" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="200">
				<spawn group="wasteland_GS200" num="1" maxAlive="1" duration="1"/>
			</gamestage>
		</spawner>
		<spawner name="burnt_forest">
			<gamestage stage="1">
				<spawn group="burnt_forest_GS1" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="50">
				<spawn group="burnt_forest_GS50" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="100">
				<spawn group="burnt_forest_GS100" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="150">
				<spawn group="burnt_forest_GS150" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="200">
				<spawn group="burnt_forest_GS200" num="1" maxAlive="1" duration="1"/>
			</gamestage>
		</spawner>
	</append>
</config>
```
The second file needing modification is `spawning.xml`. A spawner must be defined for each gamestage defined in `gamestages.xml`. The names provided in `gamestages.xml` must match the entries in `spawning.xml`.

## spawning.xml
```xml
<config>
	<append xpath="/spawning">
		<biome name="pine_forest_GS1">
			<spawn maxcount="1" respawndelay="2.9" time="Day" entitygroup="ZombiesAll" notags="commercial,industrial,downtown"/>
			<spawn maxcount="1" respawndelay="3.3" time="Night" entitygroup="ZombiesNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="2" respawndelay="0.3" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.15" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.3" time="Day" entitygroup="ZombiesForestDowntown" tags="downtown"/>
			<spawn maxcount="3" respawndelay="0.1" time="Night" entitygroup="ZombiesForestDowntownNight" tags="downtown"/>
			<spawn maxcount="2" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="1" time="Night" entitygroup="WildGameForestNight" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="3.2" time="Night" entitygroup="EnemyAnimalsForest" spawnDeadChance="0"/>
		</biome>
		<biome name="pine_forest_GS50">
			<spawn maxcount="1" respawndelay="2.9" time="Day" entitygroup="ZombiesAll" notags="commercial,industrial,downtown"/>
			<spawn maxcount="1" respawndelay="3.3" time="Night" entitygroup="ZombiesNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="2" respawndelay="0.3" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.15" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.3" time="Day" entitygroup="ZombiesForestDowntown" tags="downtown"/>
			<spawn maxcount="3" respawndelay="0.1" time="Night" entitygroup="ZombiesForestDowntownNight" tags="downtown"/>
			<spawn maxcount="2" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="1" time="Night" entitygroup="WildGameForestNight" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="3.2" time="Night" entitygroup="EnemyAnimalsForest" spawnDeadChance="0"/>
		</biome>
		<biome name="pine_forest_GS100">
			<spawn maxcount="1" respawndelay="2.9" time="Day" entitygroup="ZombiesAll" notags="commercial,industrial,downtown"/>
			<spawn maxcount="1" respawndelay="3.3" time="Night" entitygroup="ZombiesNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="2" respawndelay="0.3" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.15" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.3" time="Day" entitygroup="ZombiesForestDowntown" tags="downtown"/>
			<spawn maxcount="3" respawndelay="0.1" time="Night" entitygroup="ZombiesForestDowntownNight" tags="downtown"/>
			<spawn maxcount="2" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="1" time="Night" entitygroup="WildGameForestNight" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="3.2" time="Night" entitygroup="EnemyAnimalsForest" spawnDeadChance="0"/>
		</biome>
		<biome name="pine_forest_GS150">
			<spawn maxcount="1" respawndelay="2.9" time="Day" entitygroup="ZombiesAll" notags="commercial,industrial,downtown"/>
			<spawn maxcount="1" respawndelay="3.3" time="Night" entitygroup="ZombiesNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="2" respawndelay="0.3" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.15" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.3" time="Day" entitygroup="ZombiesForestDowntown" tags="downtown"/>
			<spawn maxcount="3" respawndelay="0.1" time="Night" entitygroup="ZombiesForestDowntownNight" tags="downtown"/>
			<spawn maxcount="2" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="1" time="Night" entitygroup="WildGameForestNight" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="3.2" time="Night" entitygroup="EnemyAnimalsForest" spawnDeadChance="0"/>
		</biome>
		<biome name="pine_forest_GS200">
			<spawn maxcount="1" respawndelay="2.9" time="Day" entitygroup="ZombiesAll" notags="commercial,industrial,downtown"/>
			<spawn maxcount="1" respawndelay="3.3" time="Night" entitygroup="ZombiesNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="2" respawndelay="0.3" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.15" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.3" time="Day" entitygroup="ZombiesForestDowntown" tags="downtown"/>
			<spawn maxcount="3" respawndelay="0.1" time="Night" entitygroup="ZombiesForestDowntownNight" tags="downtown"/>
			<spawn maxcount="2" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="1" time="Night" entitygroup="WildGameForestNight" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="3.2" time="Night" entitygroup="EnemyAnimalsForest" spawnDeadChance="0"/>
		</biome>
		<biome name="desert_GS1">
			<spawn maxcount="1" respawndelay="2.7" time="Any" entitygroup="ZombiesAll" notags="commercial,industrial,downtown"/>
			<spawn maxcount="1" respawndelay="2.1" time="Night" entitygroup="ZombiesNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="3" respawndelay="0.2" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.1" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.2" time="Day" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.09" time="Night" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="3.5" time="Any" entitygroup="EnemyAnimalsDesert" spawnDeadChance="0"/>
		</biome>
		<biome name="desert_GS50">
			<spawn maxcount="1" respawndelay="2.7" time="Any" entitygroup="ZombiesAll" notags="commercial,industrial,downtown"/>
			<spawn maxcount="1" respawndelay="2.1" time="Night" entitygroup="ZombiesNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="3" respawndelay="0.2" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.1" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.2" time="Day" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.09" time="Night" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="3.5" time="Any" entitygroup="EnemyAnimalsDesert" spawnDeadChance="0"/>
		</biome>
		<biome name="desert_GS100">
			<spawn maxcount="1" respawndelay="2.7" time="Any" entitygroup="ZombiesAll" notags="commercial,industrial,downtown"/>
			<spawn maxcount="1" respawndelay="2.1" time="Night" entitygroup="ZombiesNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="3" respawndelay="0.2" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.1" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.2" time="Day" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.09" time="Night" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="3.5" time="Any" entitygroup="EnemyAnimalsDesert" spawnDeadChance="0"/>
		</biome>
		<biome name="desert_GS150">
			<spawn maxcount="1" respawndelay="2.7" time="Any" entitygroup="ZombiesAll" notags="commercial,industrial,downtown"/>
			<spawn maxcount="1" respawndelay="2.1" time="Night" entitygroup="ZombiesNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="3" respawndelay="0.2" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.1" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.2" time="Day" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.09" time="Night" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="3.5" time="Any" entitygroup="EnemyAnimalsDesert" spawnDeadChance="0"/>
		</biome>
		<biome name="desert_GS200">
			<spawn maxcount="1" respawndelay="2.7" time="Any" entitygroup="ZombiesAll" notags="commercial,industrial,downtown"/>
			<spawn maxcount="1" respawndelay="2.1" time="Night" entitygroup="ZombiesNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="3" respawndelay="0.2" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.1" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.2" time="Day" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.09" time="Night" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="3.5" time="Any" entitygroup="EnemyAnimalsDesert" spawnDeadChance="0"/>
		</biome>
		<biome name="snow_GS1">
			<spawn maxcount="1" respawndelay="2.6" time="Any" entitygroup="SnowZombies" notags="downtown"/>
			<spawn maxcount="1" respawndelay="1.7" time="Night" entitygroup="ZombiesNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="4" respawndelay="0.09" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.06" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.07" time="Day" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.04" time="Night" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="3.1" time="Any" entitygroup="EnemyAnimalsSnow" spawnDeadChance="0"/>
		</biome>
		<biome name="snow_GS50">
			<spawn maxcount="1" respawndelay="2.6" time="Any" entitygroup="SnowZombies" notags="downtown"/>
			<spawn maxcount="1" respawndelay="1.7" time="Night" entitygroup="ZombiesNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="4" respawndelay="0.09" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.06" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.07" time="Day" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.04" time="Night" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="3.1" time="Any" entitygroup="EnemyAnimalsSnow" spawnDeadChance="0"/>
		</biome>
		<biome name="snow_GS100">
			<spawn maxcount="1" respawndelay="2.6" time="Any" entitygroup="SnowZombies" notags="downtown"/>
			<spawn maxcount="1" respawndelay="1.7" time="Night" entitygroup="ZombiesNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="4" respawndelay="0.09" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.06" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.07" time="Day" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.04" time="Night" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="3.1" time="Any" entitygroup="EnemyAnimalsSnow" spawnDeadChance="0"/>
		</biome>
		<biome name="snow_GS150">
			<spawn maxcount="1" respawndelay="2.6" time="Any" entitygroup="SnowZombies" notags="downtown"/>
			<spawn maxcount="1" respawndelay="1.7" time="Night" entitygroup="ZombiesNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="4" respawndelay="0.09" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.06" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.07" time="Day" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.04" time="Night" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="3.1" time="Any" entitygroup="EnemyAnimalsSnow" spawnDeadChance="0"/>
		</biome>
		<biome name="snow_GS200">
			<spawn maxcount="1" respawndelay="2.6" time="Any" entitygroup="SnowZombies" notags="downtown"/>
			<spawn maxcount="1" respawndelay="1.7" time="Night" entitygroup="ZombiesNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="4" respawndelay="0.09" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.06" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.07" time="Day" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.04" time="Night" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="3.1" time="Any" entitygroup="EnemyAnimalsSnow" spawnDeadChance="0"/>
		</biome>
		<biome name="wasteland_GS1">
			<spawn maxcount="1" respawndelay="0.3" time="Day" entitygroup="ZombiesWasteland" notags="commercial,industrial,downtown"/>
			<spawn maxcount="2" respawndelay="0.001" time="Night" entitygroup="ZombiesWastelandNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="4" respawndelay="0.033" time="Day" entitygroup="ZombiesWasteland" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.002" time="Night" entitygroup="ZombiesWastelandNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.0167" time="Day" entitygroup="ZombiesWastelandDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.002" time="Night" entitygroup="ZombiesWastelandDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="0.3" time="Any" entitygroup="EnemyAnimalsWasteland" spawnDeadChance="0"/>
		</biome>
		<biome name="wasteland_GS50">
			<spawn maxcount="1" respawndelay="0.3" time="Day" entitygroup="ZombiesWasteland" notags="commercial,industrial,downtown"/>
			<spawn maxcount="2" respawndelay="0.001" time="Night" entitygroup="ZombiesWastelandNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="4" respawndelay="0.033" time="Day" entitygroup="ZombiesWasteland" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.002" time="Night" entitygroup="ZombiesWastelandNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.0167" time="Day" entitygroup="ZombiesWastelandDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.002" time="Night" entitygroup="ZombiesWastelandDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="0.3" time="Any" entitygroup="EnemyAnimalsWasteland" spawnDeadChance="0"/>
		</biome>
		<biome name="wasteland_GS100">
			<spawn maxcount="1" respawndelay="0.3" time="Day" entitygroup="ZombiesWasteland" notags="commercial,industrial,downtown"/>
			<spawn maxcount="2" respawndelay="0.001" time="Night" entitygroup="ZombiesWastelandNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="4" respawndelay="0.033" time="Day" entitygroup="ZombiesWasteland" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.002" time="Night" entitygroup="ZombiesWastelandNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.0167" time="Day" entitygroup="ZombiesWastelandDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.002" time="Night" entitygroup="ZombiesWastelandDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="0.3" time="Any" entitygroup="EnemyAnimalsWasteland" spawnDeadChance="0"/>
		</biome>
		<biome name="wasteland_GS150">
			<spawn maxcount="1" respawndelay="0.3" time="Day" entitygroup="ZombiesWasteland" notags="commercial,industrial,downtown"/>
			<spawn maxcount="2" respawndelay="0.001" time="Night" entitygroup="ZombiesWastelandNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="4" respawndelay="0.033" time="Day" entitygroup="ZombiesWasteland" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.002" time="Night" entitygroup="ZombiesWastelandNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.0167" time="Day" entitygroup="ZombiesWastelandDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.002" time="Night" entitygroup="ZombiesWastelandDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="0.3" time="Any" entitygroup="EnemyAnimalsWasteland" spawnDeadChance="0"/>
		</biome>
		<biome name="wasteland_GS200">
			<spawn maxcount="1" respawndelay="0.3" time="Day" entitygroup="ZombiesWasteland" notags="commercial,industrial,downtown"/>
			<spawn maxcount="2" respawndelay="0.001" time="Night" entitygroup="ZombiesWastelandNight" notags="commercial,industrial,downtown"/>
			<spawn maxcount="4" respawndelay="0.033" time="Day" entitygroup="ZombiesWasteland" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.002" time="Night" entitygroup="ZombiesWastelandNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.0167" time="Day" entitygroup="ZombiesWastelandDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.002" time="Night" entitygroup="ZombiesWastelandDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="0.3" time="Any" entitygroup="EnemyAnimalsWasteland" spawnDeadChance="0"/>
		</biome>
		<biome name="burnt_forest_GS1">
			<spawn maxcount="1" respawndelay="2.8" time="Day" entitygroup="ZombiesBurntForest"/>
			<spawn maxcount="1" respawndelay="3.2" time="Night" entitygroup="ZombiesNight"/>
			<spawn maxcount="3" respawndelay="0.25" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.15" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.15" time="Day" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.1" time="Night" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="1.1" time="Night" entitygroup="EnemyAnimalsBurntForest" spawnDeadChance="0"/>
		</biome>
		<biome name="burnt_forest_GS50">
			<spawn maxcount="1" respawndelay="2.8" time="Day" entitygroup="ZombiesBurntForest"/>
			<spawn maxcount="1" respawndelay="3.2" time="Night" entitygroup="ZombiesNight"/>
			<spawn maxcount="3" respawndelay="0.25" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.15" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.15" time="Day" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.1" time="Night" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="1.1" time="Night" entitygroup="EnemyAnimalsBurntForest" spawnDeadChance="0"/>
		</biome>
		<biome name="burnt_forest_GS100">
			<spawn maxcount="1" respawndelay="2.8" time="Day" entitygroup="ZombiesBurntForest"/>
			<spawn maxcount="1" respawndelay="3.2" time="Night" entitygroup="ZombiesNight"/>
			<spawn maxcount="3" respawndelay="0.25" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.15" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.15" time="Day" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.1" time="Night" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="1.1" time="Night" entitygroup="EnemyAnimalsBurntForest" spawnDeadChance="0"/>
		</biome>
		<biome name="burnt_forest_GS150">
			<spawn maxcount="1" respawndelay="2.8" time="Day" entitygroup="ZombiesBurntForest"/>
			<spawn maxcount="1" respawndelay="3.2" time="Night" entitygroup="ZombiesNight"/>
			<spawn maxcount="3" respawndelay="0.25" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.15" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.15" time="Day" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.1" time="Night" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="1.1" time="Night" entitygroup="EnemyAnimalsBurntForest" spawnDeadChance="0"/>
		</biome>
		<biome name="burnt_forest_GS200">
			<spawn maxcount="1" respawndelay="2.8" time="Day" entitygroup="ZombiesBurntForest"/>
			<spawn maxcount="1" respawndelay="3.2" time="Night" entitygroup="ZombiesNight"/>
			<spawn maxcount="3" respawndelay="0.25" time="Day" entitygroup="ZombiesAll" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="4" respawndelay="0.15" time="Night" entitygroup="ZombiesNight" tags="commercial,industrial" notags="downtown"/>
			<spawn maxcount="3" respawndelay="0.15" time="Day" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="4" respawndelay="0.1" time="Night" entitygroup="ZombiesDowntown" tags="downtown"/>
			<spawn maxcount="1" respawndelay="1" time="Any" entitygroup="WildGameForest" spawnDeadChance="0"/>
			<spawn maxcount="1" respawndelay="1.1" time="Night" entitygroup="EnemyAnimalsBurntForest" spawnDeadChance="0"/>
		</biome>
	</append>
</config>
```
