# zCreator_data
Character data files for ZombieMUD zCreator. Works with Nashira's zCreator Character Creator.

## Install zCreator

Obtain a copy of Nashira's zCreator and install it. A link to a download can be found for example from the ZombieMUD Reddit page: https://www.reddit.com/r/zombiemud/ (right side panel).

## Installing updated data

To download all the data as a single archive, press the "<> Code" button, and then select "Download ZIP". After download extract the data and replace your zCreator data/ folder with the one you downloaded.

## For advanced users with Git knowledge

Clone the repository using a Git-client ("git clone"). Copy the zCreator.exe to the root path of the cloned project (the exe-file is ignored in .gitignore). Update your data by "git pull".

## Provide data updates

If you have updates, please fork the repository, make your changes, and send a pull request.

## Updating race information

### To give valid information on racial base stats updates you would need to do this cycle for 100% accuracy:
1. Select a race
2. Select required alignment and/or gender for the race, if any
3. Select `fighter` as the guild
4. Take mortal levels only up to `30`
5. Take note of output from the `stats` command
6. Go to the cleric guild and do: `list skills all`
7. Look at max % on the `consider` skill, this is the racial skill max %
8. Look at the exp cost for `weapon skill 1h bludgeon`, the racial skill cost is: (value * 100 / 300)
9. `list spells all`
10. The racial spell max % is the same as max % on `dispel curse` and the exp cost is again calculated according to `step 8` above.
11. `Reinc out` and select the `same race` again
12. Select `bard` as the guild.
13. Take mortal levels only up to `30`
14. Take note of output from the `stats` command
15. Congratulations, the lowest values on each stat compared with output from `step 5` is the racial base stats


## Updating guild/sub information

To add a new guild/subguild, add it to the "guilds.chr" file. Include the official name and maximum level of the guild/subguild.

### Guild/subguild data files have the following format:
- Level information ("info")
- Skill/spell information ("info full")
- (Optional) Subguild information

You can acquire this information by typing "info" and "info full" at the guild. To check the official name of the guild/sub, you can do "la plaque" and take note of the name. To add guild dependencies (e.g. subguils to a guild) use the following format:
```
Subguilds:
Masters_of_Defence 10
Cantadorian_Guard 7
Brawlers 5
The_Royal_Warders 6
Blademasters 5
Myrmidons 5
```

## Updating spell/skill information

Add the name and initial cost of the spell/skill to spells.chr/skills.chr/skills using the following format:
```
attack:1300
```
You can check the initial cost at a guild/sub by doing "list skills all"/"list spells all" and calculating the basic cost by taking into account your racial spell/skill cost.

Then add the spell/skill description to help_spell.chr/help_skill.chr, you can get this information by doing "help skill attack", "help spell magic missile".

