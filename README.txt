Sound Village 0.6.5
===================

A standalone app for making Marvel Rivals audio mods, from choosing the game
sound to the finished .pak. It replaces the soundKit_MR folder tool: no
numbered folders, no scripts to run, no FModel and no separate packing
program.

Up to version 0.6.4 this app was called soundKit GUI. It is the same app
under its own name.


RUNNING IT FROM THIS FOLDER
---------------------------
1. Install Python 3 from https://www.python.org/downloads/ . On the first page
   of the installer tick "Add python.exe to PATH".
2. Double-click "Sound Village.bat".
3. A setup guide opens and walks through three things:
   - Helper programs. ffmpeg (converts your audio) is too large to ship
     here. "Download ffmpeg" fetches it from its makers' GitHub page. If you
     have a soundKit folder, "Copy parts from a soundKit folder" copies it
     from there instead, together with the spoken-number test sounds.
   - The game. "Find the game" looks for Marvel Rivals, "Download the pak
     tool" fetches the small program that opens the game's archives, and
     "Get the key from the pak tool" fills in the game's key.
   - Voice lines. "Build the lists from the game" reads every voice line and
     its text from your own game.

If the window does not appear, run "Sound Village (show errors).bat" instead.
It keeps a console open so the error text can be read. Errors are also saved
in error.log in this folder.


COMING FROM SOUNDKIT GUI (0.6.4 OR EARLIER)
-------------------------------------------
Unzip this folder NEXT TO your soundKit_GUI folder (in the same folder that
holds it) and start "Sound Village.bat". The app notices the earlier copy and
asks whether to bring its things over. On a Yes it copies:
  - your settings and colours
  - the helper programs you downloaded (ffmpeg, the pak tool, wav2wem)
  - your voice-line lists and character list, if they are newer than the
    ones in this folder, and your saved sound names
  - the game's file list and event names
Everything is copied. Nothing in the old folder is changed or removed, so it
keeps working, and you can remove it by hand once you are happy with this one.
Not brought over: the results folder, and the banks and sounds copied out of
the game (the app fetches those again when it needs them).

The question is asked once, on the first start, and only while this folder
has no settings of its own.


WHAT A NEW USER NEEDS
---------------------
- Marvel Rivals installed on the same PC. The app reads the game's own files;
  nothing has to be exported first.
- An internet connection once, for the Download buttons in the setup guide.
- The pak tool needs Microsoft's .NET runtime. Windows offers to install it
  when it is missing.
- Nothing else. FModel and repak are not needed. A sound library built with
  FModel still works if you have one, but sounds play straight from the game.


MAKING A MOD, START TO FINISH
-----------------------------
Everything happens on the Mod Builder tab, in three boxes.

Box 1, Game WEMs to replace (left)
  Press the character button and pick a character. Its sound banks open by
  themselves: SFX and Voice, each on its own button. "More banks" opens other
  banks of the game (costumes, breaths, emotes, menus) or a .bnk file of your
  own.
  The list shows the bank's WEMs in groups, named after what plays them:
  reload, jump, q, ko_ace. Tick a group to replace all of it, or open the
  group and tick single WEMs. Double-click a row, or press Play, to hear it.
  The Filter field narrows the list by name, by a spoken line's words or by
  ID. "WEM Search" looks through every bank the app knows.
  Groups the game's files give no name are called "unnamed" and sit at the
  end of the list. Names come from "Build the lists from the game" on the
  Setup tab.

Box 2, Your Custom Audio (right)
  Every ticked group gets a card. "Choose audio" picks your file (wav, mp3,
  ogg, m4a or flac). One file covers every WEM of the group, so it is heard
  whichever variation the game picks. "Each gets its own" gives every WEM of
  the group a different file; "Same audio for all" goes back. "Edit audio"
  opens trimming, fades and volume on the Audio Editing tab. "Remove" takes
  the card away and unticks the group.
  A card without audio changes nothing: the game's own sound plays.

Box 3, Modded BNK (right, bottom)
  "Build modded BNK" builds the bank(s). "Save as .pak" packs them into one
  mod file: you name the mod and choose a folder once, and the folder is
  remembered like a browser's downloads folder. The file is named
  <name>_9999999_P.pak and goes in the game's ~mods folder. If something
  changed since the last build, "Save as .pak" offers to build first.

Loudness. The app never changes how loud your audio is. Volume, fades and
trimming happen only when you set them on the Audio Editing tab.

The line at the bottom of the window says what the app is doing. "Show log"
opens the full log; "Copy report" copies everything worth sending along when
something goes wrong.


AFTER A GAME UPDATE: THE UPDATES TAB
------------------------------------
A game update can add sounds to a bank. A mod built on the old bank then
silences the new ones, or stops working. The Updates tab finds those mods and
rebuilds them.

Your mods   Shows the .pak files in your mods folder that hold audio (the
            game's ~mods folder to begin with; "Change" picks another). Mods
            switched off by a mod manager (.bak_repak) are listed too.
  Made      The season the .pak was made in, from the file's date and the
            season dates in data\lists\SEASON-DATES.txt. "about" means it is
            read from the file's date; a .pak this app saved is exact.
  Changed   "Check my mods" compares each mod's bank with the game's current
            one. "Needs update" means the game has changed that bank since
            the mod was built. Checking only reads.
  Update    Rebuilds the selected mod on the game's current bank, keeping
            every sound it replaces (right-click a row for the same thing).
  Update all   Does that for every mod marked "Needs update", and for no
            other.
  Update another file   For a .pak or a modded .bnk somewhere else. That file
            is left alone and the new one is written to the job's folder.

What an update does to your mods folder: the new .pak takes the old one's
place under the same name, and the old .pak is moved into the app's Recovery
folder first. A report in the job's folder (Results tab) lists every sound
that was carried over, and any the game no longer has.

Recovery    The app's own recycle bin: every .pak an update replaced, each in
            a dated folder. "Restore" puts one back where it came from; the
            .pak that is there at that moment goes into Recovery in its
            place. The app never empties Recovery. Remove what you no longer
            want by hand ("Show in Explorer" opens it).

When a new season starts, add a line for it to SEASON-DATES.txt (the file
says how). Until then the Made column says "after Season 11" for newer mods.


THE GAME: FOLDER, PAK TOOL, KEY
-------------------------------
All three are on the Setup tab under "The game", and in the setup guide.

Game folder   Where Marvel Rivals is installed. "Find it" looks through
              Steam's and Epic's libraries on every drive. The game's own
              files are only ever read.
Pak tool      UAssetTool by X-zant (github.com/X-zant/UAssetToolRivals). The
              app starts it only to list what is inside the game's archives
              and to copy files out of them into the app's data\game folder.
              The first time it copies something out, the pak tool itself
              downloads one file it needs (oo2core_9_win64.dll, the
              decompressor the game's archives use) and keeps it beside
              itself. That download is the tool's own doing, not the app's.
Game key      The game's AES key: 64 letters and digits. It is needed to save
              a finished .pak and to open a mod .pak. It is not written into
              the program, because the game can change it. "Get it from the
              pak tool" looks for it inside the pak tool, and then in the
              soundKit's key file (data\fmodel\FModel_AES_Key.txt). A key is
              kept only if it is proven on your game: decrypting an archive's
              table of contents with it must give the checksum the archive
              itself records. You can also paste a key; a whole line such as
              "Main Static AES Key: 0x..." works. The checklist shows WRONG
              for a key that fails the proof, and no .pak is saved with it.

When the game is updated, the app notices at the next start and ASKS whether
to rebuild the lists. It never rebuilds them by itself, and a No is remembered
until the next update.


WHERE THINGS ARE
----------------
tools\      helper programs: ffmpeg, vgmstream, the pak tool (tools\paktool),
            and optionally wav2wem and the classic BNK packer
data\       ID lists, voice-line lists, season dates, test sounds
data\game\  copies of files the app pulled out of the game: its file list,
            banks and sounds. Can grow to a gigabyte or more. It holds nothing
            that cannot be fetched again, so it is safe to remove by hand
            while the app is closed.
cvs\        the original library-builder script (see below)
results\    one new folder per job, holding what the job produced and a log
Recovery\   the .pak files that updates replaced (see the Updates tab)
work\       scratch copies made while a job runs
settings.json   remembered choices
app\        the program itself (Python source)


WHAT THE APP DOES TO FILES
--------------------------
- It never changes, moves or removes the files you give it (your audio, a
  .bnk you open, a mod you pick with "Update another file"). They are only
  read.
- The game is only read. The pak tool is started with two kinds of command
  and no others: list the contents of an archive, and copy files out of an
  archive into the app's own folder.
- Everything it makes goes into a new folder under results\ or work\, or
  into data\game. "Save as .pak" writes the finished mod into the folder you
  chose and never replaces a file there: if the name is taken, it asks for
  another name.
- Downloaded helper programs go into a new folder each (tools\<program>\
  <version>). An older copy is left where it is; the app uses the newest.
- "Remove" buttons and the Delete key only take a card or a row off a list
  in the window.
- Edits made on the Audio Editing tab are a recipe kept in settings.json. Your
  audio file is not altered; "Save as a new file" writes a separate file and
  refuses to replace an existing one. Previews are made from a decoded copy
  of your file that the editor keeps in work\preview\.

Two things MOVE a file, and they are the only places where the app removes
anything:

1. Box 3 of the Mod Builder moves a modded BNK out of the app, by dragging it
   into a folder or with "Move to...". After that the app no longer has it.
   * Dragging: Windows Explorer performs the move, and asks first if a file
     of the same name is already there.
   * "Move to..." never overwrites: a file of the same name gets a number
     added.
2. The Updates tab, when you press Update, Update all or Restore, and only
   after you confirm. The old .pak moves from your mods folder into Recovery,
   and the new one moves from the job's folder into your mods folder under
   the old name. Nothing else in the mods folder is touched. The new .pak is
   written and read back in full before the old one is moved at all. If a
   step fails, the app puts the old .pak back and says what happened. A .pak
   that another program is using (the game, when it is running) is refused
   before anything is moved.

How a move is done: on the same drive it is a rename, and nothing is copied
or removed. Onto another drive, the app copies the file under a name ending
in .part, compares the copy with the original byte for byte, gives the copy
its real name, and only then removes the original. A copy that stops half
way (a full disk) or does not match keeps its .part name and the original
stays where it is; the message names the leftover, which can be removed by
hand. One routine in the app does this for both cases above, and it is the
single place in the whole app that removes a file. It accepts three kinds of
file and no other: a file inside the app's own results\ folder, a file
inside the app's own Recovery\ folder, and a .pak in your mods folder on its
way into Recovery.

- The work\ folder, old folders in results\, Recovery\, data\game\, older
  versions under tools\, app-backup-... folders left by updates, and
  data\replaced-by-import\ (earlier lists) are never cleaned up by the app.
  They are safe to remove by hand while the app is closed.
- The only files the app rewrites are its own: settings.json, its two small
  records in data\ (made-mods.json: the .pak files it saved; mods-checked.json:
  what the last check found), the job record and log inside each results
  folder, and scratch files inside work\.
- Two choices move a folder of yours, and only if you press them: "Move the
  library into the app folder" (a rename), and the "move the export in" tick
  box when building a library.

The sound library builder is the one job still done by the original soundKit
script (cvs\z1_RunMeInPowershell_CVS_MR.ps1), run out of sight by Windows
PowerShell in a fresh folder under work\. That script deletes and moves files
as part of its normal work; the app's helper stops it from doing either
outside that one work folder. "Test the script helper" on the Setup tab checks
this on your PC. The voice-line lists and the character list are built by the
app itself and do not use that script.


WHAT WAS AND WAS NOT TESTED
---------------------------
The app is written and tested on Linux. Windows programs (the pak tool,
wav2wem) and the real window toolkit cannot be run there, so they are stood in
for. What follows says plainly which is which.

NEW IN 0.6.5 AND NOT YET SEEN ON WINDOWS BY ANYONE:
- The whole new look: the tab bar, the outline buttons, the drawn play and
  tick-box pictures, the cards of box 2, the one-line status bar. All of it
  was built from sketches and checked only against a stand-in for the window
  toolkit, which knows what the toolkit accepts but cannot show a picture.
  Expect things that are misplaced, cut off or the wrong size.
- The new Mod Builder as a whole, the Updates tab, Recovery and Restore, and
  the question about an earlier copy on the first start.

Checked against real files from real installs (Season 10 and earlier):
- The built-in BNK packer rebuilds the banks of two working mods byte for
  byte from the game's banks and the mods' own sounds.
- The .pak writer rebuilds both of those mods' .pak files byte for byte, and
  the reader opens them (including a .pak with its file names stripped).
- Updating: a mod built on an older real bank (the game has since added 89
  sounds to it and removed 22) is rebuilt on the current bank with its
  replaced sounds carried over; a sound the game no longer has is reported
  as lost. A mod that is already current is recognised and left alone.
- Update and Restore with the mods folder on another drive than the app, a
  copy that does not match, a disk that fills up half way, a .pak that is in
  use, a failed write, Stop pressed half way and a wrong key: in every case
  each mod ends up either fully updated or exactly as it was. (Another drive,
  a full disk and a file in use are imitated in the test; they were not
  produced on real hardware.)
- Lists built from the game match lists built from an FModel export for two
  whole characters (1,144 identical lines; the differences are sounds FModel
  does not show).
- The game's text files read the same as FModel's export (63,942 entries).
- The correction applied to compressed sound files leaves 453 of the game's
  own compressed sounds exactly as they are, and restores one whose header
  was damaged on purpose.
- The key finder, on the real pak tool program (v1.5.9): it finds the real
  key and refuses the 678 other 64-digit codes that program holds.
- Every screen and button of this version, driven by a test with stand-ins
  for the window toolkit and for the pak tool. The stand-in pak tool answers
  with the real tool's own output, recorded on a real install. While that
  test runs, every file the app opens, writes, renames or removes is
  recorded and checked against the rules in the section above.

Confirmed on Windows 10 by the person this was built for:
- versions up to 0.5: the window, dark mode, the player, audio output
  selection, the colour picker, building a modded BNK with the classic packer,
  dragging a built BNK out, the Audio Editing tab, building the lists from an
  FModel export
- 0.6.0 to 0.6.4, on Season 10: the app finding the game, downloading the pak
  tool and starting it, building the lists from the game, the Game Sounds
  browser, WEM Search finding effects by event name, building with the
  built-in packer, Reset Colors, Copy report
- on Season 11: the app reads the updated game and lists the new character's
  banks

NOT yet confirmed on Windows:
- a .pak made by the app being loaded by the game. The one attempt so far
  was made with 0.6.0 and its wrong key, so it proves nothing either way.
  With the right key the files the app writes are byte-identical to working
  mods given the same input. At the time of writing the game cannot load any
  mod on Season 11 until the mod loader is updated, so this cannot be tried
  yet.
- the Download buttons for ffmpeg and vgmstream (the file names looked for on
  those pages are from memory)
- compressed (Vorbis) sound files with the real wav2wem. This is off unless
  switched on in Settings, each file is checked after it is made, and any
  file that does not check out is made uncompressed instead.
- the PowerShell helper, the sound library builder, the updater against a
  real GitHub repository, Build EXE.bat

If something fails, "Copy report" at the bottom of the window collects what
is needed to find out why, and the log.txt in the job's results folder says
what happened.


NOT IN THIS VERSION
-------------------
- New layouts for the other tabs. Game Sounds, Audio Editing, Tools, Results,
  Setup and Settings have the new look but are arranged as before.
- Opening an existing mod .pak to pull its clips out as loose files for
  re-use. (Updating a mod does keep the sounds it carried over, in the job's
  your-sounds folder.)
- Muting whole sets of sounds in one step.
- Voice mods without a bank. The game keeps the start of every spoken line
  inside the bank, so a bank is always needed.
- Sound-effect banks are listed when you open them, not searched as a whole:
  "WEM Search" knows spoken lines and the sounds of banks you have opened.
- Option 106 of the original tool, and the small utilities in
  3_XTRA\Misc-Tools. Several of them exist to delete files, which this app
  does not do.
- Dragging files from Explorer onto the window. Use the buttons.
- Mods that hold more than sounds. The Updates tab lists them when they hold
  a bank, but rebuilds sound-only mods.


MAKING THE .EXE VERSION FOR OTHER PEOPLE
----------------------------------------
1. Do the steps under RUNNING IT first, so that tools\ffmpeg and
   data\test-sounds are filled in.
2. Double-click "Build EXE.bat". It needs an internet connection once, to
   fetch PyInstaller.
3. Zip the folder it reports: dist\Sound-Village. People unzip that and run
   "Sound-Village.exe". They need no Python and no other download for the app.

Your own results, settings, sound library, Recovery folder and the files
copied out of your game are not copied into the build. Building again replaces
the previous contents of build\ and dist\Sound-Village (that is PyInstaller
refreshing its own output). The .exe is not code-signed, so Windows may show
an "unknown publisher" warning on other PCs.


CREDITS AND LICENSE
-------------------
Built on soundKit_MR by BruhLookAtThis / Tobi, SlimeCore / WispEnjoyer,
Lazuli / Kara and u/charles2404. soundKit_MR is licensed under the GNU General
Public License v3.0 (see LICENSE.md), and so is this app; its source is the
app\ folder. It uses vgmstream and FFmpeg, UAssetTool by X-zant (GPL-3.0) to
read the game's archives, and optionally wav2wem by pas2k and
SoundFileEditor.exe, each under its own license (see LICENSE.md and
tools\vgmstream\COPYING). vgmstream and SoundFileEditor come in this folder;
ffmpeg, the pak tool and wav2wem are downloaded from their makers' pages when
you press the button, or copied from a soundKit folder. The correction applied
to compressed sound files follows the soundKit 2.2.8 script. The season dates
come from marvelrivals.fandom.com/wiki/Seasons.


VOICE LINES AND CHARACTER LIST
------------------------------
The lists say which sound ID is which spoken line, which bank each sound
lives in, and which number is which character and costume. They change with
the game.

The simple way: Setup > "Build the lists from the game". The app reads the
name of every voice line, the sound files each one plays and the spoken text
from the installed game, taking the newest copy when a patch brought one. It
takes a few minutes the first time, because the voice banks are copied out of
the game. No FModel is involved. Characters the game's files do not name yet
but whose numbers are known are added by hand in the app (at the moment 1068
Nightcrawler and 1071 Dracula); the file says so at the top. The same job
reads the names of the game's sound events, which is where the group names in
box 1 of the Mod Builder come from.

The older way, from an FModel export, still works and is described next. It is
also how one person can publish ready-made lists for others to download.

Refreshing them from an FModel export:
  1. In FModel, with the current game loaded: open Marvel/Content, right-click
     the Localization folder and export it as .json. Then open
     Marvel/Content/Marvel, right-click the Wwise folder and export it as
     .json. Only those two folders are needed.
  2. In the app: Setup > "Build from an FModel export", keep the first choice
     (voice-line lists and the character list), pick the two exported
     folders, give the set a name such as "Season 11", and press Start.
  3. Setup > "Package lists for publishing" makes one small zip file named
     soundkit-lists-<date>-<time>.zip. Keep that name.
  4. Attach the zip to a release on the GitHub repository (see UPDATES).

Everyone else: Settings > "Check for updates". With "Check when the app
starts" ticked, newer lists are installed without asking.

Installing lists removes nothing: the lists in use become "previous" (the
tool that updates IDs from an older season uses them), and whatever was
"previous" is kept in data\replaced-by-import\.

The character list is written from the game data alone, each time the lists
are built: playable characters and costumes under the game's own display
names (so 1011 is "Bruce Banner", as the game has it), and voices the game
gives no display name (bosses, announcers, bystanders) under the game's
internal folder names, marked as approximate. Costumes the game has not really
named are left out. Changes made to the file by hand do not survive the next
build; the previous file is kept in data\replaced-by-import\.

Why the lists are built by the app now: the original tool matched spoken
lines by number alone, and the game reuses those numbers in other tables, so
some lines came out wrong (Blade's "A thousand cuts!" appeared as "Randomly
grants 2 Common cards."). The app matches on the voice table itself.


UPDATES OF THE APP ITSELF
-------------------------
Settings > "Check for updates" asks GitHub whether a newer version of the
app, or newer voice-line lists, have been published, and offers to install
them. (This is about the app. Updating your mods is the Updates tab.)

The app uses the internet for two things only, and both only contact GitHub:
this update check, and the Download buttons for helper programs (ffmpeg,
vgmstream, the pak tool, wav2wem), each of which asks before it starts.

To tell the app where updates come from, either type the repository
(owner/name) into the box in Settings, or put it on a line of its own in
update-source.txt in the app folder (do this before sharing the app, so
other people do not have to type anything). The repository must be public.

When update-source.txt names a repository, "Check when the app starts" is on
until the user switches it off in Settings; otherwise it is off. A start-up
check installs newer voice-line lists without asking, and asks before
installing a new app version.

Publishing: on the repository's GitHub page choose Releases > "Draft a new
release", give it a tag, attach the zip file, and publish.
- A new app version: tag it like v0.6.5 and attach the app's zip (it must
  contain the "app" folder).
- New lists: any tag (for example lists-season11) with the
  soundkit-lists-....zip attached. Lists can be published on their own or in
  the same release as an app version.

Installing an app update removes nothing. The current "app" folder is renamed
to "app-backup-<version>-<date>" and the new one takes its place. To go back,
close the app, rename the new "app" folder to something else and rename the
backup to "app". Tools, sounds, settings and results are never touched.
