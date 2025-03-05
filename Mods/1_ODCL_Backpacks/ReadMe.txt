#1-ODCL_Backpacks

### GER

Diese Mod führt ein Gewichtssystem ein. Zu 85% haben alle Items und Blöcke ein Gewicht. Das Startgewicht des Spielers beträgt 100 (kg) und hat 153 Inventarplätze.
Items oder Blöcke, die kein Gewicht haben, wiegen 0 (kg).
Überladen ist der Spieler, sobald er die maximale Tragekapazität überschreitet. Wiegt der Spieler 50 (kg) über der maximalen Tragekapazität, kann er nicht mehr laufen.
Steroide können dieses Problem auf Zeit beheben.
Hinzugefügt wurden 7 Rucksäcke mit verschiedenen Gewichtsgrößen. Angelegt werden sie als Mod im Outfit für die Brust. Einmal angelegt, wird dem Spieler die Tragekapazität gutgeschrieben, solange er ihn trägt.
Taschenmods erweitern die Tragekapazität ebenfalls.
Alle Rucksäcke sind im Third-Person Modus sichtbar, so wie es die Rüstung zulässt. Bei einigen Outfits ist der Rücken schon vollgepackt. Bei diesen Outfits wird das Rucksack Modell nicht angezeigt.
Die Werte werden trotzdem gut geschrieben. 
Rucksäcke kann man nicht finden oder kaufen!
Jeder Rucksack hat ein Rezept und eine Schematik. Diese Schematik besteht aus 4 Teilen. Diese Teile können gefunden werden in Containern und Zeitungsständern. Der Händler bietet sehr selten für viel Geld eines solcher Teile an.
Hat man 4 Teile des gleichen Types, kann man mit dem integrierten Designertisch die Teile zu einem Rezept zusammensetzen. Der Designertisch kann sofort über die Werkbank hergestellt werden. Es werden keine Fertigkeitsbücher benötigt.
Wurde das erstellte Rezept erlernt, kann man den Rucksack ebenfalls über die Werkbank herstellen.
Nicht immer hat man das Glück, dass Container oder Händler diese Teile vorrätig haben. Um es nicht weiter hinauszuzögern, wurde eine Buchmünze eingeführt. Erlernt man ein Rezept oder liest man ein Buch,
bekommt man Buchmünzen. Im Designertisch kann man die gesammtelten Münzen eintauschen, gegen ein kleines Päckchen mit unterschiedllicher Qualität. 
Umso höher die Qualität, umso teurer ist das Päckchen--> um so höher ist die Wahrscheinlichkeit ein seltenes Buch oder gar ein Teil des Rucksack-Rezeptes zu erhalten.

Du benutzt noch andere Mods, in denen Du Items hast, die ein Gewicht benötigen? Kein Problem.
Du benötigst dazu 2 Variablen, [ItemWeight] und [TSItemWeight].

[ItemWeight] wird zur Berechnung des Gewichtes benötigt. 1.0 ist 1 kg. / 0.1 sind 100 Grammm und so weiter. Die Mod kann bis zu 2 Stellen nach dem Komma anzeigen. 000.00 / 100 Gramm sind 0.1 im Status HUD.
[TSItemWeight] ist Verantwortlich für die Anzeige des Gewichts im HUD.

Manche Items besitzen keine Statusanzeige. Um bei diesen Items eine Statusanzeige zu aktivieren, trage diese Zeile mit ein:

<property name="DisplayType" value="TSItemDisplay"/>

Bei der Value tragt ihr den Namen ein, welcher in der UIDisplay.xml zu finden ist. Wollt ihr nur die Gewichtsangabe, dann könnt ihr [TSItemDisplay] verwenden. Bei Rüstungen und Munition sind 
es zum Beispiel [armorPrimitiveHelmet]Zeile 63 für den Primitiven Helm und [ammoBullet]Zeile 63 für Munition 9mm.
# Items.xml

## Beispiel
Das hier ist das Item "Leim" im original

<item name="resourceGlue">
	<property name="HoldType" value="45"/>
	<property name="Tags" value="junk"/>
	<property name="Meshfile" value="@:Other/Items/Misc/sackPrefab.prefab"/>
	<property name="DropMeshfile" value="@:Other/Items/Misc/sack_droppedPrefab.prefab"/>
	<property name="Material" value="Morganic"/>
	<property name="Weight" value="10"/>
	<property name="Stacknumber" value="500"/> <!-- STK resource -->
	<property name="EconomicValue" value="20"/>
	<property name="Group" value="Resources,Chemicals,CFChemicals"/>
	<property name="SoundPickup" value="glue_grab"/>
	<property name="SoundPlace" value="glue_place"/>
## Hinzufügen
	<property name="ItemWeight" value="0.5"/> <!--Berechnung-->
	<property name="DisplayType" value="TSItemDisplay"/> <!--Falls notwendig-->
		<effect_group tiered="false">
			<display_value name="TSItemWeight" value="0.5"/> <!--Anzeige im Hud-->
		</effect_group>
</item>
Unsere Resource Leim wiegt jetzt 0.5 kg.

###WICHTIG
-EAC muss aus sein!
-Score wird benötigt
-Quartz wird benötigt
-Der Original-Mod 0_TFP_Harmony wird benötigt

### ENG

This mod introduces a weight system. 85% of the time, all items and blocks have a weight. The player's starting weight is 100 (kg) and has 153 inventory slots.
Items or blocks that have no weight weigh 0 (kg).
The player is overloaded as soon as he exceeds the maximum carrying capacity. If the player weighs 50 (kg) over the maximum carrying capacity, he can no longer walk.
Steroids can temporarily solve this problem.
7 backpacks with different weight sizes have been added. They are put on as a mod in the outfit for the chest. Once put on, the player is credited with the carrying capacity as long as he wears it.
Bag mods also increase the carrying capacity.
All backpacks are visible in third-person mode, as the armor allows. In some outfits, the back is already fully packed. In these outfits, the backpack model is not displayed.
The values are still written well.
Backpacks cannot be found or bought!
Every backpack has a recipe and a diagram. This schematic consists of 4 parts. These parts can be found in containers and newspaper racks. The dealer very rarely offers one of these parts for a lot of money.
If you have 4 parts of the same type, you can use the integrated designer table to put the parts together to form a recipe. The designer table can be made immediately using the workbench. No skill books are required.
If the created recipe has been learned, you can also make the backpack using the workbench.
You are not always lucky enough that containers or dealers have these parts in stock. In order not to delay it any longer, a book coin was introduced. If you learn a recipe or read a book,
you get book coins. In the designer table you can exchange the collected coins for a small package of different quality.
The higher the quality, the more expensive the package --> the higher the probability of receiving a rare book or even part of the backpack recipe.

Do you use other mods in which you have items that require a weight? No problem.
You need 2 variables, [ItemWeight] and [TSItemWeight].

[ItemWeight] is needed to calculate the weight. 1.0 is 1 kg. / 0.1 is 100 grams and so on. The mod can display up to 2 decimal places. 000.00 / 100 grams is 0.1 in the status HUD.

[TSItemWeight] is responsible for displaying the weight in the HUD.

Some items do not have a status display. To activate a status display for these items, enter this line:

<property name="DisplayType" value="TSItemDisplay"/>

For the value, enter the name that can be found in the UIDisplay.xml. If you only want the weight, you can use [TSItemDisplay]. For armor and ammunition, for example, it is [armorPrimitiveHelmet]line 63 for the primitive helmet and [ammoBullet]line 63 for 9mm ammunition. # Items.xml

## Example
This is the item "Glue" in the original

<item name="resourceGlue">
	<property name="HoldType" value="45"/>
	<property name="Tags" value="junk"/>
	<property name="Meshfile" value="@:Other/Items/Misc/sackPrefab.prefab"/>
	<property name="DropMeshfile" value="@:Other/Items/Misc/sack_droppedPrefab.prefab"/>
	<property name="Material" value="Morganic"/>
	<property name="Weight" value="10"/>
	<property name="Stacknumber" value="500"/> <!-- STK resource -->
	<property name="EconomicValue" value="20"/>
	<property name="Group" value="Resources,Chemicals,CFChemicals"/>
	<property name="SoundPickup" value="glue_grab"/>
	<property name="SoundPlace" value="glue_place"/>
## Add
	<property name="ItemWeight" value="0.5"/> <!--Calculation-->
	<property name="DisplayType" value="TSItemDisplay"/> <!--If necessary-->
	<effect_group tiered="false">
		<display_value name="TSItemWeight" value="0.5"/> <!--Display in HUD-->
	</effect_group>
</item>
Our glue resource now weighs 0.5 kg.

###IMPORTANT
-EAC must be off!
-Score is required
-Quartz is required
-The original mod 0_TFP_Harmony is required

### Credits
Vielen Dank an SCore und Quartz Ersteller.

Alle Modelle sind von Sketchfab: (Danke an alle)

DesignTable			https://sketchfab.com/3d-models/workbench-93bf119e2bb443b49006c6b12efe06ae
Blueprints			https://sketchfab.com/3d-models/old-blueprints-4759259e450a4269a93c582dd276f1b9
Guitar Backpack 	https://sketchfab.com/3d-models/survival-guitar-backpack-799f8c4511f84fab8c3f12887f7e6b36
Leather Backpack 	https://sketchfab.com/3d-models/backpack-b9e73f29c3c54b06870cddc6ae4bf03b
Vintage backpack	https://sketchfab.com/3d-models/vintage-military-backpack-dce182b7965546118df059f90df497dc
Military backpack	https://sketchfab.com/3d-models/military-backpack---italian-army----free-2b4e4303a4ec42f69c3c91c16ea72828
Old Soviet Backpack https://sketchfab.com/3d-models/old-soviet-backpack-bb89dfa7ec13478e85645497dfeafdcd
Old backpack		https://sketchfab.com/3d-models/old-backpack-renewed-hope-d1a73335a05744a291fe6c54e8c67eec


Die Mod darf beliebig verwendet, aber nicht verändert werden. Wollt ihr etwas geändert haben, meldet euch bei mir und ich sehe, was ich machen kann.
Sie darf nicht verkauft werden.
Die Modelle dürfen nicht entwendet und für andere Dinge benutzt werden.
