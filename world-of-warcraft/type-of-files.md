# Type of files World of Warcraft uses

This document explains the type of files WoW uses and which you will need. You can ignore the rest. The tools required to open or convert these files are in the actual guides.

### Table of Contents 
* [WoW Filesystems](type-of-files.md#wow-filesystems)
* [Model files](type-of-files.md#model-files)
* [Texture files](type-of-files.md#texture-files)


## WoW Filesystems
* **MPQ** (Mo'PaQ, short for Mike O'Brien Pack, named after its creator), is an archiving file format used in several of Blizzard Entertainment's games. MPQs contain listfiles. It's been used since Warcraft 3 to Vanilla to MoP. It got replaced by CASC.

* **CASC** (Content Addressable Storage Container) is the name of the new file system that Blizzard has created to replace the outdated format of MPQ. WoW uses CASCv2. You require a list file to view the contents of CASC archive.

## Model files
* **M2** files (also called MDX) contain model objects. Each M2 file describes the vertices, faces, materials, texture names, animations and properties of one model. Models are used for doodads (decoration objects), players, monsters and really everything in the game except for Terrain and World Map Objects. M2 files don't have a chunked format like most other WoW formats (except in Legion). 
    * **.anim** files are low priority sequences (e.g. emotes, one shot animations) are in extra files to allow for lazy loading. These files are raw data of timestamps and values for animation blocks.
    * **M2i** files are just decompiled M2 files readable by Blender script. Basically something like an SMD.

* **WMO** files contain world map objects. They have a chunked structure. Generally, porting WMOs is just a huge hit and miss. It either crashes WMV or exports blank file, and the WMO 3DS Max script doesn't work most of the time. There are two types of WMO files:

    * WMO root file - lists textures (BLP Files), doodads (M2 Files), etc., and orientation for the WMO groups (World\wmo\path\WMOName.wmo)
    * WMO group file - 3d model data for one unit in the world map object (World\wmo\path\WMOName_NNN.wmo)

* **ADT** files contain terrain and object information for map tiles. They have a chunked structure. Only known way how to import ADT is via Taylor Mouse's ADT import 3DS Max's script, and it's untextured. To find out what part of ADT terrain you want to grab, just look at the minimap files.

## Texture files
* **BLP** files store textures with precalculated mipmaps. BLP files are capable of storing data with a few different formats. The primary variables are palettized/RGB and alpha bit depth. The RGB formats are actually stored using DXT compression (DXT1 for 0-bit alpha and DXT3 for the others), and thus conversion to these formats is somewhat lossy. [XnView](http://www.xnview.com) is actually able to view BLP files like it was just a regular image, but can't generate thumbnails of them in Explorer window.
