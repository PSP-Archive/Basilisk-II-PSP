# Basilisk II for the PSP

Basilisk II is a multi-platform Mac II emulator whose code is released under the terms of the GPL v2. As such, it is available on many different platforms, now including the PSP. 

Features for the PSP version include:

* Emulates a Mac II series machine running OS 7.0.1 through 8.1, depending on the ROM used.
* Uses UAE CPU emulation, with new SoftFloat FPU emulation for better compatibility.
* The PSP memstick can be mounted on the Mac desktop (requires File Manager 1.2).
* Supports on-the-fly change of colors and resolution (requires Display Manager).
* Has stereo, 16-bit, 44kHz audio (requires Sound Manager 3.0).
* Supports emulated floppy and CDROM with removable media (no CD audio yet).
* Supports up to four hardfiles for use as fixed drives.
* UDP tunnel for AppleTalk networking across WIFI (no general networking yet).
* Emulates a Mac Extended ADB keyboard and mouse. Buttons can be remapped on-the-fly, and popular IR keyboards are supported on the Phat PSP.
* Supports extra memory and TV out on the Slim PSP.

The main Basilisk II website is located at http://basilisk.cebix.net/. This version of Basilisk II is based on the JIT version found at http://gwenole.beauchesne.info//en/projects/basilisk2. My thanks go to ChaosKnight for the earlier port of Basilisk. While virtually none of his code made it into this conversion (his conversion was of a much older version of Basilisk II), it was helpful to see how he handled certain things. Thanks also to John Hauser for his SoftFloat code, which greatly improves the accuracy of the FPU emulation. I'd also like the thank BenHur for intraFont, which I use in the user interface, and Dark_AleX for his wonder custom firmware, without which homebrew wouldn't be the same, and his TV library.

Basilisk II comes with ABSOLUTELY NO WARRANTY. This is free software, and you are welcome to redistribute it under the terms of the GNU General Public License.

## Installing Basilisk II for the PSP

Copy the BasiliskII folder in the archive to the GAME, GAME3XX, or GAME4XX folder in the PSP folder of your memstick. If you look at the folder, you'll see the following:

```
(directories)
cdroms
disks
files
graphics
hardfiles
imaps
keymap
roms
(files)
EBOOT.PBP
dvemgr.prx
pspirkeyb.ini
```

The cdroms folder is where you copy the bin/cue dumps of Mac CDROMs you wish to use with the emulation. These should be standard MODE1 ISO dumps, not raw dumps. The extension for CDROM images are normally “.bin”, “.iso”, or “.img”.

The disks folder is where you copy floppy images you wish to use with the emulation. These are plain dumps of 1.44 MB high-density Mac or PC format microfloppy disks. PC format requires theappropriate Mac extension to read, such as MacLink (part of OS 8). All files in this folder should have an extension of “.dsk”.

The files folder is mounted on the Mac desktop when enabled in the settings. Files in this folder should be in AppleDouble, hqx, and binhex format.

The graphics folder contains the images used by the danzeff on-screen keyboard.

The hardfiles folder contains the files that are used as fixed hard disks in the emulation. They can be virtually any size, but will generally be between 200 and 400 MB as a basic installation of OS8 takes about 120 MB. You can have any number of files in this directory, but only a maximum of four can be selected at one time. The extension of files in this folder should b “.hfv”, but may also have no extension at all.

The imaps folder holds the input maps for remapping the PSP buttons into Mac input events. This will be explained later.

The keymap folder holds the keycode maps for IR keyboards.

The roms folder holds the Mac ROM images you might use with the emulation. You select one image in the emulation setup. They can have any file name, but a typical extension is “.rom”.

EBOOT.PBP is the PSP executable for the emulator itself.

Dvemgr.prx is the TV support library, and needs to be present for TV out on the Slim. It is not needed on a Phat PSP.

Pspirkeyb.ini is the initialization configuration file for IR keyboards with the PSP. It is set to the Palm IR keyboard. If you have a different IR keyboard, you will need to edit it with a text editor. The file has comments and it should be fairly self-explanatory.

Note: No Apple Macintosh ROMs or software of any sort is included with this program. You'll have to find them yourself. This emulator is useless without a ROM and MacOS.

## Controls

- SELECT - Invoke the imap/floppy/cdrom menu
- START - Invoke the danzeff on-screen keyboard (OSK)

While in the imap/floppy/cdrom menu, you press left/right to change between input maps, floppies, and cdroms. Press up/down to browse the list of files in the imaps, disks, and cdroms directories, respectively. Press CROSS to select an input map, or mount a CD-ROM or floppy. Press SELECT again to exit the menu. Note that you can only have one cd-rom and floppy mounted at a time. To mount another, you must first dismount the CD-ROM/floppy which is already mounted. On the Mac, you dismount disks/cd-roms by throwing them in the trash, or by selecting the disk and then selecting Eject from the Special menu (or pressing the Command + E keys).

While the danzeff OSK is active, the controls are as follows:

- CROSS/SQUARE/CIRCLE/TRIANGLE - generate key from selected box
- RTRIGGER - shift key
- LTRIGGER - switch between letters and numbers
- UP - delete
- DOWN - enter
- LEFT/RIGHT - move the danzeff OSK to the left/right side of the display
- ANALOG STICK - select a box

Press SELECT to change the qualifier key generated along with the key. The qualifiers are NONE, COMMAND, OPTION, CONTROL, and COMMAND + OPTION. Press START again to exit the danzeff OSK

### Default Controls

- CROSS – mouse button
- SQUARE – enter key
- CIRCLE – command + w (Close Window)
- TRIANGLE – command + q (Quit Application)
- RTRIGGER – control key
- LTRIGGER – option key
- UP/DOWN/LEFT/RIGHT – corresponding cursor key
- ANALOG STICK – mouse

### dpad_mouse Controls

- CROSS – mouse button
- SQUARE – enter key
- CIRCLE – command + w (Close Window)
- TRIANGLE – command + q (Quit Application)
- RTRIGGER – control key
- LTRIGGER – move mouse faster
- UP/DOWN/LEFT/RIGHT – mouse
- ANALOG STICK – mouse

### Maelstrom Controls

- CROSS – fire
- SQUARE – shields
- CIRCLE – thrusters
- TRIANGLE – play game
- RTRIGGER – pause game
- LTRIGGER – abort game
- LEFT/RIGHT – turn ship left/right
