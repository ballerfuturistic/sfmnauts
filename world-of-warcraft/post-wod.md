# Porting models from Post-Warlords of Draenor WoW client

This lists all of the known ways how to port models from WoD and Legion WoW Clients. **Tested with the latest retail release of Legion, which at the time of writing is 7.2.5.** 

Also, please remember that trying to get a WMO
### Table of Contents
* [Easy way - Using WMV](Using-WoW-Model-Viewer)
* [The harder way - Manual extract](Manual-extract)

## Using WoW Model Viewer
WoW Model Viewer is an application developed by Jerommimo that allows you to view and export WoW models.
For WoD, you want version **0.8.5**, and for Legion, just get the latest unstable alpha release. [You can find the list of downloads here](https://wowmodelviewer.net/wordpress/?page_id=27).

The usage is pretty straightforward. To export a model, go to file -> Export model -> FBX.

**Please be aware that you have to fix normals on the model and have to clean up useless bones when importing.** 

If you end up with a model with no textures, just use the export textures dialog, or export as OBJ. At the time of writing, the unstable release is able to export animations, but doesn't work most of the time, or is just broken. Keyframes are there but no animation.

![3DS Max animation timeline](/world-of-warcraft/img/timeline.png)

Also female worgen models are just broken, not a problem of the exporter lmfao. Pls go yell at blizzard to fix them. Thank.

## Manual Extract

So, you have decided to take the hardest route, huh? I hope you have enough RAM.

The manual extract procedure is almost the same as with pre-WoD.

Tools required:
* [BLP2PNG](http://www.wowinterface.com/downloads/info6127-BLP2PNG.html)
* [M2ModRedux](https://bitbucket.org/suncurio/m2mod/downloads/), alternatively, [Original M2Mod](http://www.mediafire.com/file/uuvi6jonoz7un2u/M2Mod_470b.zip)
* [CascView](http://www.zezula.net/en/casc/main.html)
* [WoW CASC Listfile](https://github.com/bloerwald/LegionFiles)
* [Blender](https://www.blender.org/)
* [Blender M2i scripts](https://bitbucket.org/suncurio/blender-m2i-scripts/downloads/)
* [Alternatively, 3DS Max M2 script](https://www.dropbox.com/s/hoiqm0n3u4ybdqs/TaylorMouse-Adt-Wmo-ImportScript.zip)
* Hex editor of choice

Simplified usage of said tools:
* Install M2i Blender scripts
* Use CASCView to extract WoW data to a folder (Can eat up RAM pretty quickly)
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
Here's a YT video by the man himself. **DO NOT** even attempt to import Legion WMOs or M2s with this script. Trust me, it's gonna crash 3DS Max or just spit out ton of errors. WMO and M2 support for this script is purely for WoD.

[![Import World of Warcraft ADT, WMO, M2 files into 3D Studio Max](http://img.youtube.com/vi/mQTJMy0ebjU/0.jpg)](https://youtu.be/mQTJMy0ebjU)

If you encouter code errors even with XnConvert location set, convert all of the textures to PNG with BLP2PNG. This should solve this.
