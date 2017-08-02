# Porting models from Pre-Warlords of Draenor WoW client

This lists all of the known ways how to port models from old versions of WoW. **Using retail MoP 5.4.8 client is recommended, as this guide is written this exact version.** The last definitive version of MoP client before WoD pre-patch is 5.4.8.18414. The only reason why I would even suggest using it is just Machinima Studio. It might be dead but it's still pretty powerful toolset.


### Table of Contents
* [Easy way - Using WMV](pre-wod.md#Using-WoW-Model-Viewer)
* [Easy way - Machinima Studio (Paid)](pre-wod.md#Machinima-Studio)
* [The harder way - Manual extract](pre-wod.md#Manual-extract)

## Using WoW Model Viewer
WoW Model Viewer is an application developed by Jerommimo that allows you to view and export WoW models.
You want FBX export, and the last version of WMV for MPQ based clients with working FBX export is version 7.0.5. [You can download it from the official site here](https://wowmodelviewer.net/wordpress/?wpdmpro=wowmodelviewer_7-0-5).

The usage is pretty straightforward. To export a model, go to file -> Export model -> FBX.

**Please be aware that you have to fix normals on the model and have to clean up useless bones when importing.**

## Machinima Studio

**WARNING: Machinima studio's last update was in 2011, is a paid program, the developer has abandoned the program AND the developer has killed the registration servers. I would strongly advise against on purchasing this program because there's a great chance that you won't get anything in return. To manually reset the 30 day period, Open Regedit, navigate to "SoftwareBCMachinimaStudio" and remove "feedbackUrl"**

Machinima studio is an application that can export WMOs with doodads, ATDs and M2s without a problem. It's pretty powerful. [You can download it from here](http://www.machinimadev.com/download/). Make sure to also check out the [tutorial section](http://www.machinimadev.com/tutorials/).

![profile select](/world-of-warcraft/img/profile_select.png)

When you launch the application, load the WoW plugin and add your MoP Client. You can safely ignore the warnings about incompatible client, it handles 5.4.8 without any problem with my testing.

Follow the application's tutorial how to export models.

## Manual Extract

So, you have decided to take the hardest route, huh?

Tools required:
* [BLP2PNG](http://www.wowinterface.com/downloads/info6127-BLP2PNG.html)
* [M2ModRedux](https://bitbucket.org/suncurio/m2mod/downloads/), alternatively, [Original M2Mod](http://www.mediafire.com/file/uuvi6jonoz7un2u/M2Mod_470b.zip)
* [MPQ Editor](http://www.zezula.net/en/mpq/download.html)
* [Blender](https://www.blender.org/)
* [Blender M2i scripts](https://bitbucket.org/suncurio/blender-m2i-scripts/downloads/)
* [Alternatively, 3DS Max M2 script](https://www.dropbox.com/s/hoiqm0n3u4ybdqs/TaylorMouse-Adt-Wmo-ImportScript.zip)
* Hex editor of choice

Simplified usage of said tools:
* Install M2i Blender scripts
* Use MPQ Editor to extract WoW data to a folder
* Drag the whole folder of extracted data to BLP2PNG to convert all textures
* Grab an M2 file you want to port
* Use M2Mod to decompile the M2 and generate M2i
* Import said M2i into Blender (and alternatively export to FBX to throw into 3DS Max)
* Find the model textures by opening up the file in hex editor and finding the data.

From [Wowdev Wiki](https://wowdev.wiki/M2#Textures)
>Textures are defined globally in a list, additionally, a lookup table is given, referenced during rendering, to select textures.



```
struct M2Texture

{
  uint32_t type;          // see below
  uint32_t flags;         // see below
  M2Array<char> filename; // for non-hardcoded textures (type != 0), this still points to a zero-sized string
} textures[];

```



And yes, you can totally make WoW titty mods with M2ModRedux.

### How to use Taylor Mouse's 3DS Max scripts
Here's a YT video by the man himself.

[![Import World of Warcraft ADT, WMO, M2 files into 3D Studio Max](http://img.youtube.com/vi/mQTJMy0ebjU/0.jpg)](https://youtu.be/mQTJMy0ebjU)

If you encouter code errors even with XnConvert location set, convert all of the textures to PNG with BLP2PNG. This should solve this.
