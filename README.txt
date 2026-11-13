Sound Village 0.6.7.9
=====================

Make audio mods for Marvel Rivals: pick a game sound, give it your own audio,
and get a finished .pak. The app reads the game directly, so there is nothing
to export and no other modding tool to install.


STARTING
--------
1. Unzip the folder anywhere and run "Sound-Village.exe".
   Windows may warn about an unknown publisher: click "More info", then
   "Run anyway".
2. A setup guide opens. Press its buttons from left to right:
   - Find the game
   - Download the pak tool (a small program that opens the game's files)
   - Get the key from the pak tool
   - Build the lists from the game (a few minutes the first time)
   If Windows asks to install Microsoft's .NET runtime, say yes. The pak tool
   needs it.

You need Marvel Rivals installed on the same PC, and an internet connection
for the Download buttons. The guide can be opened again from the Setup tab.


MAKING A MOD
------------
Everything happens on the Mod Builder tab, in three boxes.

1. Game WEMs to replace
   Press the character button and pick a character. Its sound banks open by
   themselves. The list shows the game's sounds in groups named after what
   plays them (reload, jump, q). Tick a group to replace all of it, or open
   it and tick single sounds. Double-click a line to hear it. The Filter
   field and "WEM Search" find a sound by name, spoken words or ID.

2. Your Custom Audio
   Every ticked group gets a card. "Choose audio" picks your file (wav, mp3,
   ogg, m4a or flac). One file covers the whole group; "Each gets its own"
   gives every sound of the group a different file. "Edit audio" opens
   trimming, fades and volume. The app never changes how loud your audio is
   unless you move a control.

3. Modded BNK
   "Build modded BNK", then "Save as .pak". Name the mod and choose a folder.
   The finished file goes in the game's ~mods folder.

Not sure which sound is which? On the Tools tab, "Test sounds" makes sounds
that speak a number. Put those in a mod, play the game, and the number you
hear tells you which sound it was.


AFTER A GAME UPDATE
-------------------
A game update can change a sound bank, and a mod built on the old bank may
stop working. The Updates tab fixes that.

- "Check my mods" looks at the audio mods in your mods folder and marks the
  ones the update left behind as "Needs update". Checking only reads.
- "Update" rebuilds the selected mod on the game's current bank and keeps
  every sound you replaced. "Update all" does it for every mod marked
  "Needs update".
- The new .pak takes the old one's place under the same name. The old one is
  moved into the Recovery folder inside the app's folder first. "Restore"
  puts it back.
- Close the game before updating: a .pak the game is using cannot be moved.
- The app never empties Recovery. Remove old files there yourself when you
  no longer want them.

When the game is updated, the app notices at the next start and asks whether
to rebuild its lists. Say yes; it takes a few minutes.


WHAT THE APP DOES TO YOUR FILES
-------------------------------
- Your audio files are only read, never changed.
- The game's own files are only read.
- Everything the app makes goes into its own folder, or into the folder you
  choose for a finished .pak. It never replaces a file there.
- It removes nothing, with one exception you ask for: moving a file. Moving
  a built bank out with "Move to...", or an Update or Restore on the Updates
  tab, moves a file from one place to another. Across two drives the app
  copies it, checks the copy byte for byte, and only then removes the
  original.
- It uses the internet only for the Download buttons and for "Check for
  updates" in Settings, and both only contact GitHub.


IF SOMETHING GOES WRONG
-----------------------
The line at the bottom of the window says what the app is doing. "Show log"
opens the details. "Copy report" copies everything needed to work out what
happened; paste that when you ask for help.

Common causes:
- "Game key WRONG" on the Setup tab: the game changed its key. Press "Get it
  from the pak tool", or download the pak tool again to get a newer one.
- Group names are missing in the Mod Builder: press "Build the lists from
  the game" on the Setup tab.
- A mod shows "Cannot be checked" on the Updates tab: the reason is in the
  last column.


FOLDERS INSIDE THE APP'S FOLDER
-------------------------------
results\    what each job produced, one folder per job
Recovery\   the .pak files that updates replaced
data\game\  copies of files read out of the game; can grow large and is safe
            to remove while the app is closed
work\       scratch files; safe to remove while the app is closed
settings.json   your choices and colours


UPDATES OF THE APP
------------------
Settings > "Check for updates" looks for a newer version and offers to
install it. Installing removes nothing: the old program folder is kept
beside the new one.


LICENCE
-------
Sound Village is free software under the GNU General Public License v3.0
(see LICENSE.md), and its source code comes with it. It uses FFmpeg,
vgmstream, UAssetTool by X-zant and SoundFileEditor, each under its own
licence.
