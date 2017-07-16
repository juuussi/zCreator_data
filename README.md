# zCreator_data
Character data files for ZombieMUD zCreator. Works with Nashira's zCreator Character Creator.

## Install zCreator

Obtain a copy of Nashira's zCreator and install it. A link to a download can be found for example from the ZombieMUD Reddit page: https://www.reddit.com/r/zombiemud/ (right side panel).

## Installing updated data

To download all the data as a single archive, press the "Clone or download" button, and then select "Download ZIP". After download extract the data and replace your zCreator data/ folder with the one you downloaded.

### For advanced users with Git knowledge

Clone the repository using a Git-client ("git clone"). Copy the zCreator.exe to the root path of the cloned project (the exe-file is ignored in .gitignore). Update your data by "git pull".

## Provide data updates

If you have updates, please fork the repository, make your changes, and send a pull request.

### Updating race information

Add the information on the races.chr. Note: You should be on level 30 to gain the actual stats that you should include in this file. You also should not have any glevels, or if you do, you need to remove stats/regen gained from glevels from your stats.

### Updating guild/sub information

Guild/subguild data files have the following format:
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

