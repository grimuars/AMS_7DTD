# Gamestaged Scout Zombies
IDC Core allows for the scouts spawned by the game to be gamestaged instead of choosing from a static group. This allows the scout zombies to be more difficult the higher the player's gamestage. This feature does NOT change how screamer hordes are spawned. This feature is disabled by default and can be enabled in the `IDCCore\Config\blocks.xml` file. This feature is also customizable via the use of entitygroups and spawners. A default setup for this feature is provided and can be used as a reference.

# Customizing Scout Groups
There are three files you will need to modify if you want to customize this feature. The first file is `entitygroups.xml`. You can define any number of entitygroups for use with this feature. Although not required, it is highly recommended to use the naming convention used in the example below.
## entitygroups.xml
```xml
<config>
	<append xpath="/entitygroups">
		<entitygroup name="scoutZombiesGS1">
		zombieScreamer
	</entitygroup>
		<entitygroup name="scoutZombiesGS50">
		zombieScreamer
		zombieScreamerFeral, 0.2
	</entitygroup>
		<entitygroup name="scoutZombiesGS100">
		zombieScreamer, 0.5
		zombieScreamerFeral, 0.5
	</entitygroup>
		<entitygroup name="scoutZombiesGS200">
		zombieScreamerFeral, 0.5
		zombieScreamerRadiated, 0.5
	</entitygroup>
		<entitygroup name="scoutZombiesGS300">
		zombieScreamerFeral, 0.4
		zombieScreamerRadiated, 0.7
	</entitygroup>
		<entitygroup name="scoutZombiesGS400">
		zombieScreamerRadiated
	</entitygroup>
		<entitygroup name="scoutZombiesGS500">
		zombieScreamerRadiated
	</entitygroup>
		<entitygroup name="scoutZombiesGS600">
		zombieScreamerRadiated
	</entitygroup>
	</append>
</config>
``` 
The second file requiring modification is `gamestages.xml`. The spawner name must be left untouched or the feature will not function properly. Any number of gamestages can be defined here as long as valid entitygroups are provided. The `num`, `maxAlive`, and `duration` attributes should all be `1`.
## gamestages.xml
```xml
<config>
	<append xpath="/gamestages">
		<spawner name="ScoutGamestagedSpawner">
			<gamestage stage="1">
				<spawn group="scoutZombiesGS1" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="50">
				<spawn group="scoutZombiesGS50" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="100">
				<spawn group="scoutZombiesGS100" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="200">
				<spawn group="scoutZombiesGS200" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="300">
				<spawn group="scoutZombiesGS300" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="400">
				<spawn group="scoutZombiesGS400" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="500">
				<spawn group="scoutZombiesGS500" num="1" maxAlive="1" duration="1"/>
			</gamestage>
			<gamestage stage="600">
				<spawn group="scoutZombiesGS600" num="1" maxAlive="1" duration="1"/>
			</gamestage>
		</spawner>
	</append>
</config>
```

The final file needing modification is `spawning.xml`. The entityspawner name MUST match the entitygroup name or errors will be thrown.
## spawning.xml  
```xml
<config>
	<append xpath="/spawning">
		<entityspawner name="scoutZombiesGS1" dynamic="true" wrapMode="wrap">
			<day value="*">
				<property name="ResetToday" value="true"/>
				<property name="EntityGroupName" value="scoutZombiesGS1"/>
				<property name="Time" value="Any"/>
				<property name="DelayBetweenSpawns" value="1"/>
				<property name="TotalAlive" value="1"/>
				<property name="TotalPerWave" value="1"/>
			</day>
		</entityspawner>
		<entityspawner name="scoutZombiesGS50" dynamic="true" wrapMode="wrap">
			<day value="*">
				<property name="ResetToday" value="true"/>
				<property name="EntityGroupName" value="scoutZombiesGS50"/>
				<property name="Time" value="Any"/>
				<property name="DelayBetweenSpawns" value="1"/>
				<property name="TotalAlive" value="1"/>
				<property name="TotalPerWave" value="1"/>
			</day>
		</entityspawner>
		<entityspawner name="scoutZombiesGS100" dynamic="true" wrapMode="wrap">
			<day value="*">
				<property name="ResetToday" value="true"/>
				<property name="EntityGroupName" value="scoutZombiesGS100"/>
				<property name="Time" value="Any"/>
				<property name="DelayBetweenSpawns" value="1"/>
				<property name="TotalAlive" value="1"/>
				<property name="TotalPerWave" value="1"/>
			</day>
		</entityspawner>
		<entityspawner name="scoutZombiesGS200" dynamic="true" wrapMode="wrap">
			<day value="*">
				<property name="ResetToday" value="true"/>
				<property name="EntityGroupName" value="scoutZombiesGS200"/>
				<property name="Time" value="Any"/>
				<property name="DelayBetweenSpawns" value="1"/>
				<property name="TotalAlive" value="1"/>
				<property name="TotalPerWave" value="1"/>
			</day>
		</entityspawner>
		<entityspawner name="scoutZombiesGS300" dynamic="true" wrapMode="wrap">
			<day value="*">
				<property name="ResetToday" value="true"/>
				<property name="EntityGroupName" value="scoutZombiesGS300"/>
				<property name="Time" value="Any"/>
				<property name="DelayBetweenSpawns" value="1"/>
				<property name="TotalAlive" value="1"/>
				<property name="TotalPerWave" value="1"/>
			</day>
		</entityspawner>
		<entityspawner name="scoutZombiesGS400" dynamic="true" wrapMode="wrap">
			<day value="*">
				<property name="ResetToday" value="true"/>
				<property name="EntityGroupName" value="scoutZombiesGS400"/>
				<property name="Time" value="Any"/>
				<property name="DelayBetweenSpawns" value="1"/>
				<property name="TotalAlive" value="1"/>
				<property name="TotalPerWave" value="1"/>
			</day>
		</entityspawner>
		<entityspawner name="scoutZombiesGS500" dynamic="true" wrapMode="wrap">
			<day value="*">
				<property name="ResetToday" value="true"/>
				<property name="EntityGroupName" value="scoutZombiesGS500"/>
				<property name="Time" value="Any"/>
				<property name="DelayBetweenSpawns" value="1"/>
				<property name="TotalAlive" value="1"/>
				<property name="TotalPerWave" value="1"/>
			</day>
		</entityspawner>
		<entityspawner name="scoutZombiesGS600" dynamic="true" wrapMode="wrap">
			<day value="*">
				<property name="ResetToday" value="true"/>
				<property name="EntityGroupName" value="scoutZombiesGS600"/>
				<property name="Time" value="Any"/>
				<property name="DelayBetweenSpawns" value="1"/>
				<property name="TotalAlive" value="1"/>
				<property name="TotalPerWave" value="1"/>
			</day>
		</entityspawner>
	</append>
</config>
```