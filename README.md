# YewMiiTools
Tool to help simplify conversion between 3DS/WiiU Mii and TLoZ:BoTW's UMii. Works with both the Switch and Wii U versions.

### Please use the (better) Mii to Umii tool by TheGreatRambler: https://github.com/TheGreatRambler/Mii_to_UMii

Compiled Binaries/Tools: https://github.com/EBLeifEricson/YewMiiTools/releases/  
GBATemp thread & discussion: https://gbatemp.net/threads/yewmiitools-conversion-from-mii-to-botws-umii.580355

At the moment, there's still a few steps, but I plan to combine some of these steps to make it even easier. Also, I think I might be incorrectly converting the eye and eyebrow rotation values-- they don't seem to just directly copy over? If anyone can tell me how to convert them properly, please let me know.

**There are some cosmetic values that do not exist in BotW. I plan to account for this eventually, but if your game crashes or the NPC is missing, try removing glasses, makeup, etc.**

## Usage
1. Place desired NPC .sbactorpack file(s) from extracted game files into the same folder as the tool. These can be found in /romfs/Actor/Pack/, see here for NPC names: https://gbatemp.net/threads/botw-item-names-for-pandaonsmacks-trainer.463959/
2. Place your **3DS/WiiU formatted** .mii file(s) into the same folder as the tool. (Right now, I use a jank method of copying the temp.mii file generated by this tool: https://gbatemp.net/threads/release-mii2studio-convert-any-mii-to-the-mii-studio-format-and-render-miis-as-pngs.575422/ If you know of a better way, *please* let me know.)
3. Run "yewmiiconv.exe" and select option 1 to extract all sbactorpack files.
4. Run the tools again. Select option 2 and follow the prompt to convert the Mii file(s) to UMii. First, drop the extracted NPC directory (or type/paste it in). Then, drop (or type/paste) the Mii file you wish to inject. 
5. The script should now have replaced the .bumii file inside the extracted NPC folder you chose.
7. Now, select option 3 in the tool to rebuild the NPC folder(s). It will prompt you to specify whether you use the Wii U or Switch version format.
8. The script will generate "OriginalNPCName.out.sbactorpack". This is your final file that can be put back into the game files or loaded with LayeredFS. (Be sure to remove the .out part)

I originally wrote this as an exercise to read Mii files from scratch (without using any other code/libraries). The other conversion tasks for this project are achieved using external bundled tools though:
* BotWUnpacker by Shadsterwolf https://github.com/Shadsterwolf/BotWUnpacker
* BotW-aampTool by Zer0XoL https://github.com/Zer0XoL/BotW-aampTool

This is probably *far* from the most efficient way to do this conversion, but it works for my own purposes.

## FAQ

1. The NPC disappears after I replace the file.

This is likely caused by an incompatible value of your Mii. For example, the nose *must* be above the mouth, and it does not support sunglasses (thanks @HEYimHeroic for those discoveries.) Edit your Mii and try again.

2. Windows Defender is detecing the file as a virus.

This tends to happen with certain applications, but Python-based exe's especially. You might have to manually allow the file, or run using the python script if you feel uncomfortable.

## Source
If you wish to instead run the script from source, then you'll have to download the two tools mentioned above yourself (BotWUnpacker and BotW-aampTool) and place them in a subfolder called "tools". The script shouldn't have any extra library dependencies.

## Planned Features
* Integrate OpenEAD library (https://github.com/zeldamods/oead) to eliminiate external tool depedency
* Auto check for invalid UMii values and correct them (or notify user)
* Transfer more parameters such as body size and height

## Examples
Dio Brando
![Dio](https://i.imgur.com/RANgWrH.jpg)
Reggie Fils-Aime
![Reggie](https://i.imgur.com/BUpPJNE.jpg)
LeifEricson
![Leif](https://i.imgur.com/AKm773Y.jpg)
