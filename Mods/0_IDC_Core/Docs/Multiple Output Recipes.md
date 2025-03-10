# Multiple Output Recipes
## Multiple Output Recipes
IDC Core allows for recipes to have multiple outputs. These outputs will automatically be displayed on the crafting UI to indicate to users what items a recipe will create.
## Defining Multiple Outputs
Defining multiple outputs on a recipe is simple. An additional output on a recipe is defined as follows:
```xml
<secondary_output name="<item name>" count="<count>"/>
```
An example recipe is provided below:
```xml
		<recipe name="ammoArrowStone" count="1">
			<secondary_output name="ammoArrowIron" count="2"/>
			<secondary_output name="ammoArrowExploding" count="5"/>
			<ingredient name="resourceSmallStone" count="2"/>
			<ingredient name="resourceWood" count="1"/>
			<ingredient name="resourceFeather" count="1"/>
		</recipe>
```
The above example will produce 1 stone arrow, 2 iron arrows, and 5 exploding arrows when crafted. Recipes can have up to 5 total output items.
## Recipe Output UI Tab
IDC Core automatically adds a tab to the crafting window to show what a recipe will create. This works with vanilla recipes and modded recipes.
![]()
