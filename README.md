# 📦 Download & Support
If you enjoy this project, consider supporting me with a donation or a kind word.

<a href="https://irmaosver-ehotmailcom.itch.io/desert-strike-ex/purchase">
<img src="https://img.shields.io/badge/Download_on_Itch.Io-fa5c5c" width="215" />
</a>

Feedback is always welcome and helps me keep building better hacks.

---

# DesertStrikeMDHack

Rom hack of *Desert Strike* for the Mega Drive adding 6-button + SRAM support

---

## Version History

**v1.4**
- Bug fix: overriding a save of a previously cleared stage would lock following unlocked stages

**v1.3**
- Bug fix: stage 3 mission 8 bus not turning when mode pressed

**v1.2**
- Bug fix: loading campaign still has MIA copilot locked after rescue
- Bug fix: mission 3 shows 2 power plants on the map
- Bazooka soldier height value adjusted; was causing a collision with the chopper on a lower altitude

**v1.1**
- Bug fix: mission 4 unlocked shows a random high score

---

## Required Original ROM

- **SHA-1**: `D7E7D8C358EB845B84FB08F904CC0B95D0A4053D`
- **CRC32**: `67A9860B`

---

## Hack Features

- A more robust save system, "campaign mode"
- Stage unlocked for selection in the main menu when cleared in "campaign mode"
- Per-stage high score displayed on the main menu
- 6-button support
- Implements the unused altitude control code found in the original ROM
- Copilot bios shortened/altered to reflect their effect on the range attributes
- Description of copilot range attributes added to their bios
- Copilot winch activation values spread further apart to show noticeable differences in gameplay
- Copilots are marked as TDY (Temporary Duty Yonder) until unlocked in "campaign mode"
- The location of MIA copilot "Carlos" was changed
- Copilot select menu activated at every stage change (unless starting stage from main menu with a non-MIA copilot)
- Flying without a copilot sets range attributes to very low
- Number of lives carried over to the next stage
- Game restarts to title screen after game over

---

## Controls

- Holding **Mode** activates strafing (makes strafing and firing missiles possible)
- **Mode + X** = Lower altitude  
- **Mode + Y** = Adjust altitude toward default  
- **Mode + Z** = Increase altitude  

---

## Copilot Effects

The effect of the copilot on helicopter behavior could not be found in any official manuals. Available info was vague and left players unsure if different copilots made a difference.

This has now been clarified. The copilot affects:
- The **distance for target auto-lock**
- The **radius for winch activation**

These values are now displayed in the bios.

Originally, winch radius values were so close that differences in gameplay were negligible. This has been adjusted for more noticeable effects.

---

## SRAM Support: Campaign Mode and Practice Mode

Once a level is cleared, it becomes selectable via **Left/Right** on the main menu.  
The original password system is still functional.  
Saving occurs when the cleared stage screen (showing the password) is displayed.

### Campaign Mode

**A level is entered in campaign mode when:**
- An **SRAM-saved** password is used

**Steps:**
1. Select the unlocked stage from the main menu  
2. Press **A** to enter the password menu; SRAM password loads automatically  
3. Press **Start** to return to main menu; stage select is disabled  
4. Press **Start** again to begin in "campaign mode"  

> To cancel: Enter password menu, alter the password, and press enter. You’ll return to main menu with stage select re-enabled.

If the selected copilot is MIA in the campaign, the copilot select screen will appear before the stage begins.

**Campaign Mode Features:**
- Always active when starting from stage 1
- Saves copilot state
- Saves number of lives
- Saves full score (fixes bug where scores <1000 lost digits)
- Only overwrites save if new score is higher (saves best runs)

---

### Practice Mode

**A level is entered in practice mode when:**
- Selected from unlocked stages  
- A non-SRAM password is used (e.g. from the internet)

**Practice Mode Rules:**
- Starts with default 3 lives (or 5/10 if lives password used)
- Stage score starts at 0 (or from password)
- Clearing a stage moves to next, but progress is **not saved**
- Stages cleared are **not** unlocked on the main menu
- Copilots unlocked only for current session
- MIA copilot is temporary and only usable in the current session
- MIA copilot **not unlocked** with non-SRAM passwords
