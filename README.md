Please consider supporting:

<a href="https://www.buymeacoffee.com/nani16bit" target="_blank">
  <img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" width="150" />
</a> 
or 
<a href="https://github.com/sponsors/irmaosver-e" target="_blank">
<img src="https://img.shields.io/badge/GitHub%20Sponsors-brightgreen" width="215" />
</a>

# DesertStrikeMDHack
Rom hack of Desert Strike for the Mega Drive adding 6button + SRAM support

version history
v1.4
* bug fix - overriding a save of a previously cleared stage would lock following unlocked stages

v1.3
* bug fix - stage 3 mission 8 bus not turning when mode pressed

v1.2
* bug fix - loading campaign still has MIA copilot locked after rescued.
* bug fix - mission 3 shows 2 power plants on the map.
* bazooka soldier height value adjusted, was causing a collision with the chopper on a lower altitude

v1.1
* bug fix - mission 4 unlocked shows a random high score.

required original ROM:

File/ROM SHA-1: D7E7D8C358EB845B84FB08F904CC0B95D0A4053D

File/ROM CRC32: 67A9860B

hack features:

• a more robust save system, "campaign mode".
• stage unlocked for selection in the main menu when cleared in "campaign mode".
• per stage high score displayed on the main menu
• 6 button support.
• implements the unused altitude control code found in the original ROM
• Copilot bios shortened/altered to reflect their effect on the rage attributes.
• A description of the copilot range attributes was added to the bio.
• copilot winch activation values spread further apart to have a more obvious difference in gameplay.
• copilots are marked as TDY (Temporary Duty Yonder) until unlocked by clearing missions in "campaign mode"
• The location of MIA copilot "Carlos" was changed.
• Copilot select menu activated at every stage change unless starting stage from the main menu with a non-MIA copilot.
• flying the helicopter without a copilot sets range attributes to very low
• number of lives carried over to the next stage.
• The game restarts to the title screen after the game over screen.

------------------------
controls:
holding "mode" activates strafing  (makes strafing and firing missiles possible)
holding "mode" + X = lower altitude.
holding "mode" + Y = lower / increase altitude towards default.
holding "mode" + Z = increase altitude.

---------------------
Copilot effects:
The effect of the copilot on the helicopter behaviour could not be found in any of the manuals. what info was available was very subjective and left the player confused and wondering if there even was any difference in picking different copilots. 

The code has been investigated to finally find out exactly what difference each copilot makes on the helicopter's behaviour, which is,  the distance for the target auto-lock to activate and the radius for the winch to activate, this is now displayed along with their bios.

Originally the winch activation radius for different copilots was so close to each other that the activation distance difference in gameplay was practically the same, only pixels apart, this has been increased to give a more tangible feel of each copilot effect in gameplay.

------------------
SRAM support, "campaign mode" and "practice mode"

Once a level is cleared it becomes available for selection by pressing left or right on the main menu.
The original password functionality has been retained.
Saving occurs when the cleared stage screen showing the password is displayed.

A level is activated in "campaign mode" when:
• An SRAM saved password is entered.

A level is activated in "practice mode" when:
• Selected from the unlocked stages.
• Selected after a non-SRAM saved password is entered  (i.e. password taken from the internet)

how to enter a "campaign mode" saved stage:
1 - select the unlocked stage from the main menu
2 - Press "A" to enter the password menu, and the SRAM saved password will automatically load.
3- press "Start",  you will be taken back to the main menu and stage selection is disabled.
4- Press Start at the main menu to begin the level in "campaign mode"
* -  to cancel "campaign mode" re-enter the password menu, alter the password auto-loaded password and press enter, you will be taken back to the main menu and level select is reenabled.
(this step can be done at any point) - choose one of the unlocked copilots, if he was left MIA in the campaign the copilot select stage will trigger before the stage starts.

"campaign mode" explained:
• when starting from stage 1 "campaign mode" is always active, 
• when a stage is cleared, the copilot state is saved.
• the number of lives saved
• the full score is saved (originally password saved scores would not carry over values lower than 1000, i.e. your cleared stage score was 12300, restarting the game from a password will restore only 12000) 
• If a new playthrough is started the previous save will only be overeaten if the current score is higher than the previous for that stage. (saved campaign stages prioritize the best scores)

"practice mode" explained:
• the player starts with the default 3 lives (5 or 10 if extra lives password was used)
• The stage score starts at 0 if entering a stage by selecting an unlocked one.
• The stage score starts at the amount set by password if entering a stage after entering a non-SRAM saved password.
• clearing a stage takes the player to the next but no progress is saved.
• stages cleared will not be unlocked for selection at the main menu
• clearing stages only unlock copilots for the current playthrough, not permanently unlocked at the main menu.
• MIA copilot can be found and selected at the next stage but only for the current playthrough, not permanently unlocked at the main menu.
• MIA copilot is not unlocked when a non-SRAM saved password is entered.
