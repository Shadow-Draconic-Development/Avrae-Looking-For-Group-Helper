<h1>Settings Subalias<img align="right" src="../../Data/image.png" width="100px"></h1>

This subalias allows you to customize what is being shown whenever a player runs the alias, if you do not alter any settings (or don't alter settings properly), they do have default values.

## How to edit settings
Editing settings requires administrative permissions.

Two options:
- Editing the dictionary directly (`lfg_settings`):

    Here is an example dictionary with default values. You do not need every value, only values you want to change:

```json
{
    "subclass": 1, 
    "thp": 1, 
    "img": 1, 
    "player": 0, 
    "ac": 0, 
    "ins": 0, 
    "inv": 0, 
    "perc": 0, 
    "spell_list": 0, 
    "spell_slot": 0, 
    "full_subclass": 0, 
    "color_lvl": {"0": ""}, 
    "response_req": 0
    }
```
- Use the settings subalias to edit values

    Simply type `alias settings` and then add `-<setting name> <setting value>` for each setting you want to change.
    I.e. I want to change subclass and thp, I simply type `alias -subclass 1 -thp 1`

    If you are wanting to change the color_lvl setting, type `-color_lvl "<level#>|<Hex code>" -color_lvl "<level#|<Hex code>"`
    I.e. if I want level 1 being #00FFFF, level 10 being #FF0000, and level 20 being #F00F00 I type `-color_lvl "1|#00FFFF -color_lvl 10|#FF0000 -color_lvl 20|#F00F00"` and it will update the dictionary entry to `{"1":"#00FFFF", "10":"#FF0000", "20":"#F00F00"}`

### subclass
- Default: On
- This determines whether or not subclass is displayed or not alongside the character's class.
- In order for this to work properly you need to do one of the following:
    - Subscribe to [Verbose Character Tools](https://avrae.io/dashboard/workshop/5f7385fe647bb0a416316d1d). Then run `!level sub ABC` (ABC is the sourcebook code, refer to `!help level` or the workshop site for codes). Then after that, run `!level class subclass`
    - Create a cvar named "subclass" and use the following template: `{classLevel: subclass, class2Level: subclass}`

### thp
- Default: On
- This determines whether or not temporary hit points are displayed with hp.

### img (Character portrait display)
- Default: On
- This determines whether or not the character's portrait (if any) is displayed as a thumbnail photo.

### player (Player is mentioned)
- Default: Off
- This detemines whether or not the player is mentioned. Automatically changes if the player changes their display name.

### ac
- Default: Off
- This shows the character's AC.

### ins (Passive insight)
- Default: Off
- Displays passive insight.
- In order for observant to apply properly, you have to have a cvar named `feats` and have 'observant' in the cvar. Recommended to have [Verbose Character Tools](https://avrae.io/dashboard/workshop/5f7385fe647bb0a416316d1d) and run `!manage feats add observant`.

### inv (Passive investigation)
- Default: Off
- Displays passive investigation

### perc (Passive Perception)
- Default: Off
- Displays passive insight
- In order for observant to apply properly, you have to have a cvar named `feats` and have 'observant' in the cvar. Recommended to have [Verbose Character Tools](https://avrae.io/dashboard/workshop/5f7385fe647bb0a416316d1d) and run `!manage feats add observant`.

### spell_list
- Default: Off
- Displays the entire spell list. This only works if the character has spells in the first place.

### spell_slot
- Default: Off
- Displays the available and used spellslots. This only works if the character has spells in the first place.

### full_subclass
- Default: Off
- Experimental
- Displays the full wording of the subclasses. I.e. Oath of Conquest Paladin rather than just Conquest Paladin.
- Requires subclasses to be enabled.

### color_lvl (Border color based upon character level)
- Default: {"0": ""} (None)
- Sets the border color of the embed card to match a certain color depending on what level the character is.
  
### response_req
- Default: Off
- Requires players to give a response. I.e. lfg \<insert response here>

## How to view settings
Simply put in `alias setting <page_num/setting_name>` (leaving blank shows all settings on seperate pages)