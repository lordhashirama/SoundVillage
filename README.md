<h1 align="center">Sound Village</h1>

<h2 align="left">DISCLAIMER: This tool was created and refined with the use of AI.
Everything generated from this tool is the product of you, the user, however.</h2>

Make audio mods for Marvel Rivals even easier: select a game sound, give it your own audio, and get a finished `.pak`.
The app reads the game directly, so there is nothing to export and no other modding tool to install.
It also keeps your installed mods in order: folders, On/Off switches, and adding mods from a download.

Windows 10 and 11. Free software (GPL v3). The source code comes with every download.

<h2 align="center">A Special Thank You: Thank You, Tobi</h2>

Sound Village exists because of SoundKit, made by Tobi (BruhLookAtThis). SoundKit made Marvel Rivals audio modding something accessible to anyone willing to learn, and it's where I learned it. Sound Village is a different way of doing the same things: it's a GUI with buttons instead of folders and scripts, but the foundational ideas (including half of the tools found in the Tools tab) were introduced to me by SoundKit. If SoundKit OR Sound Village helped you too, you can thank him at [ko-fi.com/bruhlookatthis](https://ko-fi.com/bruhlookatthis).

<h2 align="center">Download and Start</h2>

1. Download `Sound-Village.zip` from the [latest release](../../releases/latest) and unzip it anywhere.
2. Run `Sound-Village.exe`. Windows may warn about an unknown publisher: click **More info**, then **Run anyway**.
3. A setup guide opens. Press its buttons from left to right: **Find the Game**, **Download the Pak Tool**,
   **Get the Key From the Pak Tool**, **Download the Voice-Line Lists**.

You need Marvel Rivals installed on the same PC, and an internet connection for the Download buttons.

Already have Sound Village? You do not need this download. The app updates itself: **Settings > App Updates > Check for Updates**.

<h2 align="center">What It Does</h2>

**Home.** Your mods, in folders you make yourself, each with an On/Off switch. *On Now* shows what goes into the game.
Add a mod by dropping a `.pak`, `.zip`, `.7z` or `.rar` on the tab. Launch right into Rivals from the Home tab.

**Mod Builder.** Four steps: select a character's VO or SFX (or both), add your audio, build the bank, pack the mod.
The game's sounds are listed by what plays them (a voice line, an ability, a footstep), so you replace the sound you mean.

**Audio Editor.** Lanes and clips on one timeline, with Audacity's keys: cut, fade, layer, change speed and pitch,
noise cleanup, EQ, compressor, echo. Put a game sound beside your mix to compare. Export goes straight to the Mod Builder's Step 2.

**Tools.** Nine small jobs: find out which sound is which, look inside a bank or a mod, silence sounds,
replace many sounds with one, convert audio, edit a mod you already have, and clean up what the app left behind.

**Mod Updates.** After a game update the app checks your audio mods by itself and says which ones need rebuilding.
One button rebuilds them on the game's current sound banks and keeps every sound you replaced.
The old version of each mod is kept, and can be put back.

**Built-in Anti-cheat.** Certain sounds in a mod are tested with the game's own. If the mod fails a test, the mod is refused until changes are fixed (with an option to fix certain sounds automatically). 

**Themes.** Six themes come with the app under **Settings > Look**. You can mix your own and share one as a line of text.

<h2 align="center">What It Will Not Do</h2>

- It never changes your audio files or the game's own files. Both are only read.
- It never deletes anything without asking. One button deletes outright ("Delete for Good" in Clean Up Loose Files),
  only what you ticked, only in the app's own folder, and only after a box that names every file.
- It contacts GitHub and nothing else: for the helper programs, for updates, and for the voice-line lists.
  Every download is checked against the checksum the app expects before it is unpacked.
- It writes to the Windows registry only if you say yes to opening project files by double-click
  (four entries for your own user account on your computer, purely cosmetic and listed before anything is written).
- Sound Village will not allow mods to make certain game sound events louder or longer than the game's default.

The manual (`README.txt`, also under **Settings > About**) says exactly what the app does to your files.

<h2 align="center">Updates</h2>

The app looks for a newer version when it starts and offers it on the Home tab; nothing is installed by itself.
An update keeps the version before it, and if a new version cannot start, the app offers to go back.
When a newer `.exe` is published, the app asks once whether to move to it; nothing of yours moves.

<h2 align="center">If Something Goes Wrong</h2>

The **Log** tab shows what the app did, job by job, and says what went wrong in plain words.
**Save Troubleshooting Log** writes one `.zip` you can attach to an issue here on GitHub. A box lists what goes into it first.
The game key and your account IDs are never in it; your sounds are in it only if you tick them.

<h2 align="center">Thanks</h2>

The Village Hidden in the Sound stands on the work of a lot of people. Thank you to every one of them.

- **Tobi (BruhLookAtThis)**, for SoundKit, which all of this grew from (see the top of this page).
- **Wispenjoyer_ and Kara**, for the research SoundKit was built on.
- **XzantGaming (X-zant)**, for UAssetTool, which opens the game's archives and packs every mod.
- **The vgmstream developers**, for vgmstream, which plays the game's own sounds.
- **The FFmpeg developers** (FFmpeg was started by Fabrice Bellard), for FFmpeg, which converts your audio; and
  **Gyan Doshi (GyanD)**, whose Windows builds of FFmpeg the app downloads.
- **The creator of SoundFileEditor**, for SoundFileEditor, the classic BNK packer the app can still use.
- **The Audacity team** (Audacity was started by Dominic Mazzoni and Roger Dannenberg), for Audacity: the Audio Editor
  drew heavy inspiration from it.
- **Igor Pavlov**, for 7-Zip and its published description of the .7z format, which the app's own .7z reader follows.
- **Rasmus Andersson**, for the typeface Inter Display, and **Google and Adobe**, for Noto Serif CJK: the
  lettering of the Sound Village name and the signs is drawn from them.
- **The Python developers and the PyInstaller team**: Sound Village is written in Python, and PyInstaller turns
  it into `Sound-Village.exe`.

<h2 align="center">Licence</h2>

Sound Village is free software under the GNU General Public License v3.0 (see `LICENSE.md`).
FFmpeg, vgmstream and UAssetTool are each under their own licence.
The two typefaces are under the SIL Open Font License; no font file is part of the app.

Sound Village is a fan-made tool. It is not affiliated with Marvel or NetEase.
