## Notes

This guide will be based around 3DSMax, since that's what I use, but everything should pretty much be the same!

According to **huntingrifle** on **Facepunch**

1. Unpacking the meshes gave two file formats, .mesh and .model, of which only .model is needed. Trying to import .mesh files crashes 3DS Max 2012 \(and I'm assuming any version of Max\), except for a few static models which had literally no difference compared to the .model format. I don't have Maya to check if it happens there as well, but as I said, here's no difference even if you could import it. I only included the .model formats in the download link.

**Also, a couple of models under the dynamic -- mostly humanoids and anything that seems to have complex rigging crashes on import.**

**For those dynamic models that crash, try importing .mesh instead, it seems to work sometimes.**

## Importing

Importing is honestly pretty straightforward, after installing the plugin, make sure you restarted 3DSMax.

Then simply go to **file -&gt; import** and import the **.model**

## Assigning Textures

So, it turns out the **Material Editor** shows us what texture we need!

Simply **open the Material Editor** and **scroll down until you find "scene materials"** and voila!

You have now found the texture you need.

That's one method, however there's a **better method.**

**Import your mesh and then save your scene.**

You can now press **Shift+T which opens Asset Tracking** in 3DSMax which will open a list of missing textures. If you **right click it**, and hit **set path** you can more easily define the path to your textures. Just set the **path to the folder** in the **path category** and then **filename.dds** in the **file category.**

For Metro, if you use the **texture converter** linked [**in the Tools section**](/metro-redux/tools.md), you can run it in **every single folder with the textures** and then **simply change the output to .dds for each texture listed under the Asset Tracking menu.**

You run it by dragging a relevant texture file on to it. If you run it in the main directory, it will go through all subdirectories.

Considering reading the [**Texture Conversion**](/metro-redux/texture-conversion.md) guide from here on out.

