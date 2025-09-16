## [0.0.4] - 2025-mm-dd - Woodcutting Rework pt1.2

A continuation of work on the [[Woodcutting Rework Part 1]] project.  

### known issues
- problem with spirit of the grove repeatedly spawning
- issue with forester dialogue about life
- 'tree health' is being tracked globally rather than per player, so when 20 people are chopping a tree someone is gonna get lucky. this will get fixed in the final push for woodcutting rework project. 
- activity panel not having a real start
- achievements only showing up to level 10
### todo
- replace ::wcactivity with something real
### Added  
* added axeman’s folly and axeman’s folly m to Forester’s Grove Token Exchange (cost of 25/250) 
* added new potion types to PotionData:  
  * WEAK_SKILL(3, 0),  
  * NORMAL_SKILL(5, .10F),  
  * SUPER_SKILL(7, .20F),  
  * EXTREME_SKILL(10, .20F)  
* added axeman folly and matured variant to `PotionData` using `normal_skill` and `extreme_skill` boosts, and a guaranteed Spirit of the Grove spawn.  
* added Extreme Woodcutting potion to PotionData. TODO client sided changes and server sided-data changes for the items (currently uses null IDs).  
* added extreme wc potions to ItemDefinitions client sided.  
* added `::grovetier (number)` command to change grovetier.  **temporary**
* added `GroveForesterDialogue`, including options to upgrade the tier of the grove and to open the grove token exchange.  
* to upgrade the grove tier, you must have completed x% of achievements (25/50/80/99%) and spend a certain amount of grove tokens.  
* added woodcutting capes and hood (costs 1m gp) to grove equipment shop.  
* added mahogany trees and logs
* added WoodcuttingActivityPanel.
	* tracks all players wc stats
	* includes tree health/ icons for hatchet used/tree being chopped, and progress bar till next log
  
### Changed  
* removed wilderness requirements from looting bag  
  * changed spirit of the grove loot to be a guaranteed item.  
* updated woodcutting skill guide  
* changed woodcutting tutor to be the main shop npc, and the forester to be the grove token npc.  
* updated the grove map, looks nicer now. more makeup to come in the future  
* big rewrite of Woodcutting Bonuses System.  
* gave all trees MUCH more health, making logs a lot slower to obtain.  
* SIGNIFICANTLY boosted the critical hit chance with felling axes.from 1-5% up to 55-75%  
### Fixed  
* updated PlayerAssistant skillRestore() method to include all skills instead of just combat skills.  
* added grovetier to player persist file and db scripts.  
* fixed a bug where when your inventory was empty you would stop chopping, but left it where if you drop an item you’ll continue chopping.  