## Player Leveling Customization
IDC Core features the ability to set the required amount of XP required to level on a per level basis. The number of skill points given per level can also be customized.

The following example sets the XP required for to level up the for the first ten player levels. Reaching level ten also grants two skill points instead of the default one. The `exp_to_level` is **cumulative**. This means that to go from level two to level three, only an additional 1000 XP is required. If a level is not defined in the level table, vanilla behavior will be followed when calculating XP to the next level and the skill points to give.
```xml
<level max_level="300" exp_to_level="10000" experience_multiplier="1.05" skill_points_per_level="1" clamp_exp_cost_at_level="60">
	<level_table>  
		<level value="1" exp_to_level="0"/>  
		<level value="2" exp_to_level="1000" skill_points="1"/>  
		<level value="3" exp_to_level="2000" skill_points="1"/>  
		<level value="4" exp_to_level="4000" skill_points="1"/>  
		<level value="5" exp_to_level="7000" skill_points="1"/>  
		<level value="6" exp_to_level="11000" skill_points="1"/>  
		<level value="7" exp_to_level="16000" skill_points="1"/> 
		<level value="8" exp_to_level="22000" skill_points="1"/>  
		<level value="9" exp_to_level="29000" skill_points="1"/>  
		<level value="10" exp_to_level="37000" skill_points="2"/>  
	</level_table>
</level>
```
