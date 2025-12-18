# Guideline on how to deal with save related problems

There are five possible situations when the topic is “save problems” with 100% Orange Juice, and it all depends on the message you get:

1) In case you got no message at all, some of your data is weird **AND** you didn't play the game for a bit of time before coming back (read as, the last time you played was before **June 2024**) (and *didn't notice before*, or you have just run the tool described on item 5), your save data got accumulated incompatibilities under the old format (**user.dat**) and it's a miracle it didn't crash the game while loading! In this case not much can be done about it, but if the corruption is somewhat blocking you from playing the game, contact a Fruitbat on Discord or send us an e-mail on support@fruitbatfactory.com with your user.dat file, and we will do everything possible to help you.

2) In case you got the message **"There was a problem processing the save load, the game will now close to preserve your data"**, contact us with your user.dat and save folder as soon as possible, the likelihood of this message is extremely low, but in case it appears, a bug is the cause, no doubt, and it needs to be investigated.

3) In case you got the message **"While trying to load your save data, the game discovered that a profile was externally corrupted in some way"**, the situation is simple, your data was corrupted in some way that **isn't** related to the game, it's probably caused by hardware failure or external modifications. In this case, you can restore a backup, and everything should be ok! Below you can find how to do so!~

4) In case you are playing on a Linux device now (or played with Proton before), and somehow ended up with both a Save and save folders on your game directory, delete the save and rename the Save to save as soon as possible or restore a backup from this path (%APPDATA%/FBF/100OrangeJuice) under Proton (if you played with it before) or your Windows device. The path on Proton is likely ~/.local/share/Steam/steamapps/compatdata/282800/pfx/drive_c/users/steamuser/AppData/Roaming/FBF/100OrangeJuice.

5) Missing Save Data (Pre-June 2024)

   - As of **2025/12/18**, we have officially retired support for the legacy save format (**user.dat**). This change allows us to further optimize in-game data handling, since the old system that dates back to 2009, when the game scope was a thousand times smaller.

   - How to recover your save **(Windows)**: If you last played before June 2024 and find your save data missing, you can convert it manually. With Steam running, navigate to the game's installation folder and run **100orange_save.exe** located inside the **tools** folder.

   - **macOS and Linux Users:** Due to technical limitations, the conversion tool is only available on Windows. If you cannot access a Windows PC to convert your save, please contact a member of the Fruitbat team on Discord or email your user.dat file to **support@fruitbatfactory.com**. We will be happy to convert it for you!


# How to restore a backup (the manual way)

A backup of each profile is generated at the game's user data directory, the location of this folder depends on your operational system:

- **Windows**: %APPDATA%/FBF/100OrangeJuice
- **Linux**: ~/.local/share/FBF/100OrangeJuice
- **macOS**: ~/Library/Application Support/FBF/100OrangeJuice

Inside this directory, each time a profile is successfully loaded by the game, a backup is generated! Exactly at:
**{User Data Directory}/save/backup/profile{0,1,2}/{Your Steam ID}_{UNIX Timestamp from backup time}.ojs**

You just need to copy the file from the specific profile you want to restore to the game folder at:
**{Game Folder}/save/{Your Steam ID}/profile{0,1,2}.ojs**

If you don't have much notion of UNIX Timestamps, you may sort the files by most recent change and pick the newest one.

***BE SURE TO EXECUTE THE COPY OPERATION WITH THE GAME CLOSED!***


# How to restore a backup (the automated way, beta, currently available for Windows only)

- You can find it directly on the game folder at **{Game Folder}/tools**, but can also download it from here: [OJ Backup Manager](https://github.com/FruitbatFactory/100-Orange-Juice/raw/refs/heads/main/help/OJBackupManager.zip)
- Execute it
- You should be able to see three columns and two buttons!

***FIRST AND FOREMOST CLOSE THE GAME, YOU WON'T BE ALLOWED TO DO ANYTHING WHILE THE GAME IS OPEN!***

1) Use the Select Game Dir Button
(You can find the game directory via right-click on the game entry on Steam, and then Manage and then Explorer Local Files)

2) Select your Steam user on the first column

3) Select your desired profile on the second column (just add a 1 to the number, and it will be the corresponding in order inside the game)

4) Select the backup moment on the third column

5) Restore and confirm, and you are ready to go!

# Conclusion

Your problem should be solved, hopefully! If it is, have a nice day!

If it isn't, contact us (on Discord or send us an e-mail on support@fruitbatfactory.com) with a ZIP File containing your save folder and your backup folder at the **{User Data Directory}**, and if you used OJ Backup Manager, the folder "backup" that was created inside the program folder (it doesn't overwrite the target save files without backing them up first, doesn't matter if they are corrupted or not). You may create an issue here as well, but remember its public, so to preserve your save data privacy, you may find preferable to contact us directly.
