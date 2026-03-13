# Guidelines for Resolving Save-Related Issues

How would you describe your problem?

1) [The last time I played was before **2024/06/01** and my data is **gone**](#converting-old-save-data)
2) [I am seeing a message **"There was a problem processing the save load, the game will now close to preserve your data"**](#internal-logical-corruption)
3) [I am seeing a message **"While trying to load your save data, the game discovered that a profile was externally corrupted in some way"**](#external-corruption)
4) [I am having issues with Steam Cloud Sync](#solving-cloud-sync-problems)
5) [I want to restore a backup](#how-to-restore-a-backup)
6) [My save appears on Windows but not on Linux and/or Steam Deck](#case-corruption)
7) [Something else](#contact-us)

## Converting Old Save Data

As of **2025/12/18**, we have officially retired support for the legacy save format (popularly known as **user.dat**). This change allows us to further optimize in-game data handling, as the old system dates back to 2009, when the game's scope was a thousand times smaller. To have your save data brought over to the new era, you will need a **Windows PC**, if you don't have access to a **Windows PC**, you can simply [contact us](#contact-us) and we will deal with it for you. If you have a **Windows PC**, follow the steps below:

1) Make sure Steam is running
2) Navigate to the game's installation folder (Right-click in Steam > Manage > Browse local files)
3) If you have already run the game (and noticed you didn't have any save data), you will have a save folder at the root, delete the entire folder. **Do not just empty it! The folder itself must be removed**.
4) Go inside the **tools** folder, and execute **100orange_save.exe**
5) Open the game normally, and your save should be there, if it isn't, or in case it seems corrupted or some part of the game crashes, the old save might have accumulated some kind of corruption, so [contact us](#contact-us) ensuring you include your `user.dat`, and we will evaluate your situation.

## Internal Logical Corruption

[Contact us](#contact-us) with your user.dat (if any) and save folder as soon as possible. The likelihood of this message appearing is **extremely low**; however, if it does appear, it is undoubtedly caused by a bug and needs to be investigated.

## External Corruption

The situation is simple, your data was corrupted in some way that ***isn't*** related to the game, it's probably caused by hardware failure or external modifications. In this case, you can restore a backup, and everything should be OK! Click [here](#how-to-restore-a-backup) to discover how.

## Case Corruption

If you are playing on a Linux device (like the Steam Deck) now, but previously played on Windows or via Proton, you may have ended up in a situation where Steam is syncing a **"Save"** folder on Windows, with upper case **S**. While this isn't an issue on Windows, on Linux due to its case sensitivity, the game won't be able to load that folder. If you see both a **Save** and a **save** folder, delete the lowercase one and rename the uppercase **Save** to lowercase **save**. You can also manually [restore a backup](#how-to-restore-a-backup) from `%APPDATA%/FBF/100OrangeJuice` on your Windows system or `~/.local/share/Steam/steamapps/compatdata/282800/pfx/drive_c/users/steamuser/AppData/Roaming/FBF/100OrangeJuice` on your Linux device.

## How To Restore a Backup

There are 3 ways of restoring backups, select the one that works best for you:

1) [The Manual Way](#the-manual-way)
2) [The Automated Way (Windows Only)](#the-automated-way-windows-only)
3) [The Automated Way (CrossPlatform)](#the-automated-way-crossplatform)

---

### The Manual Way 

A backup of each profile is generated in the game's user data directory. The location of this folder depends on your operating system:

- **Windows**: `%APPDATA%/FBF/100OrangeJuice`
- **Linux**: `~/.local/share/FBF/100OrangeJuice`
- **macOS**: `~/Library/Application Support/FBF/100OrangeJuice`

A backup is generated inside this directory every time a profile is successfully loaded. You can find them at:
`{User Data Directory}/save/backup/profile{0,1,2}/{Your Steam ID}_{UNIX Timestamp from backup time}.ojs`

The files are named using UNIX timestamps (e.g. 1234567890). These look like long strings of random numbers, but they actually represent the date and time. The higher the number, the more recent the backup.

Simply copy the file of the specific profile you want to restore into the game folder at:
`{Game Folder}/save/{Your Steam ID}/profile{0,1,2}.ojs`

***BE SURE TO EXECUTE THE COPY OPERATION WITH THE GAME CLOSED!***

If you are unfamiliar with UNIX Timestamps, you may sort the files by most recent change and pick the newest one.

---

### The Automated Way (Windows Only)

1) You can find it directly in the game folder `{Game Folder}/tools`, but can also download it from here: [OJ Backup Manager](https://github.com/FruitbatFactory/100-Orange-Juice/raw/refs/heads/main/help/OJBackupManager.zip)
2) Execute it
3) You should be able to see three columns and two buttons!

***FIRST AND FOREMOST, CLOSE THE GAME. YOU WILL NOT BE ABLE TO MAKE CHANGES WHILE THE GAME IS RUNNING!***

1) Use the Select Game Dir Button
(You can find the game directory by right-clicking the game in Steam > Manage > Browse local files)
2) Select your Steam user on the first column
3) Select your desired profile in the second column (Note: add 1 to the number to match the order shown inside the game)
4) Select the backup moment on the third column
5) Restore and confirm, and you are ready to go!

---

### The Automated Way (CrossPlatform)

1) Go to the properties of the game on Steam and add the following to the "Launch Options": `%command% --applet=orange_juice_save`
2) Run the game via Steam
3) You will find an interface that will allow you to restore a backup in a similar fashion to [The Automated Way (Windows Only)](#the-automated-way-windows-only)

The interface also allows you to do a manual backup to the Steam Cloud, that can be restored on any device automatically, under "Online Backup".

## Solving Cloud Sync Problems

The best way to solve Cloud Sync problems is by disabling the feature in the game properties on Steam, [restoring a backup](#how-to-restore-a-backup), and finally enabling Cloud Sync again.

## Contact Us

If you encountered a problem, were instructed to contact us, or have any questions, contact us on Discord ([invite link](https://discord.gg/fruitbatfactory)) or send us an e-mail on `support@fruitbatfactory.com`! Make sure to include the relevant files related to your problem and explain all the steps you already tried!
