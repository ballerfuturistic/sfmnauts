## Credits
	Figment - Updated NifTools tools
	ShadeAnimator - Fallout 4 Animation Kit, original guide for importing animations in to max
	Mars - Starting this site and helping with this tutorial.
	Bizz - Figuring out the process for making 32bit skeletons, writing this tutorial.

##Required Files


<<<<<<< HEAD
[Custom F4Animation.hko](https://github.com/ballerfuturistic/sfmnauts/raw/master/fallout-4/file/F4Animation.zip)
download and unzip
=======
>>>>>>> b6cdda51892aeccbda72a4c819f2272884ab0e8c

[Fallout 4 Animation Kit](/fallout-4/tools.md)

[Niftools](/fallout-4/tools.md)

### Table of Contents
* [Part 1: Creating a win32 Skeleton](animations.md#part-1-32-bit-skeleton)
* [Part 2: Converting Animations to 32bit](animations.md#part-2-32bit-animations)
* [Part 3: Converting 32bit animations to FBX](animations.md#part-3-converting-hkx-animations-to-fbx)

## Part 1: 32 Bit Skeleton

We’ll be using HKXPackUi (located in the animation toolkit)  to convert the animations in to FBX, but in order to do that, we need a 32bit skeleton.hkx file. We do this by starting with the 64bit skeleton.

After deciding what character you want to convert (found in MESHES/ACTORS), find it’s skeleton.hkx file in the CharacterAssets folder.

Drag the skeleton.hkx in to HKXPackGUI and hit HKX <=> XML

![Puush button](/fallout-4/img/hkxpackGUI.png)


The bones have to be in a very specific order. The only way to get the order is taking the 64bit skeleton, so you must take it from the XML.

Look for hkaSkeleton and delete everything that isn't the bone definitions.
Isolate all the bones. Maintaining the order. It's easy to do this using notepad++, as seen here:

{% video width="640", height="480" %}/fallout-4/vid/isolatebones.mp4{% endvideo %}

Then, at the top of the file, add these two lines:

	[HAVOK SKELETON DEFINITION FILE]

	[BONES START]

At the bottom, add the following:
	[END]

<<<<<<< HEAD
[Example Feral Ghoul rig.txt](https://github.com/ballerfuturistic/sfmnauts/blob/master/fallout-4/file/feralghoulrig.txt)
=======

>>>>>>> b6cdda51892aeccbda72a4c819f2272884ab0e8c

Once you've isolated all the bones, you can save the file as skeleton.txt, or whatever other name you want to give it.

Open up 3DS Max, Import a new file, and now import the skeleton.nif file for your desired actor, this is the same place we found the skeleton.hkx.

With this loaded now,

Click Havok Content Tools along the top of 3DS max and hit “Export”. A new window will pop up

Click File -> Open configuration set and Load the provided custom F4Animation.hko (found at the top of this page)

(Not the one included in the Fallout 4 animation kit, I’ve made my own set)

Select "ExportSceneHkx" under Configuration set.

Create Skeletons

Under Build Rig select "From File" and select Use File Order.

![Build the rig from the text file we made](/fallout-4/img/buildarig.png)

Then select the skeleton text file we made earlier.

From this point, you may see a set of warnings get spit out by the output log

![The bones are missing!!!](/fallout-4/img/MissingBones.png)

If so, it means that some of the bones are missing from the scene, or are misnamed. Copy the error log and put it into notepad because we can’t edit the scene with the Content Tools open, so close it, and click "yes" to save the configuration set.

The easiest way to fix the missing/misnamed bones is to open the Scene Explorer..


In 3DSMax,
Select Tools -> "New Scene Explorer" and a list of all of the objects in the scene will pop up.

Looking at the output log to reference bones that are missing, you’ll see that it says “LThigh” is missing, but in the scene, you have “LTHIGH”. This is because the bone names are case sensitive, so the capitalization must match up. Just select

    LTHIGH

and rename it to

    LThigh

Make sure to do this for all misnamed bones. If after correcting all of the bones, but there are still some missing such as camera bones or animobjects, you can simply create a dummy with the name of the missing
bone.

You can do this by going to Create>Helpers>Dummy.

Make sure to link it to the root bone by dragging the dummy under the root bone in the scene explorer.


Now that we have no more errors about writing the skeleton, select “Write To Platform” in the configuration set, and on the right, input where you want the file to save. Once that’s done, hit
“Run Configuration” and your 32bit skeleton will be created.

**Note:**
You should save the scene with this skeleton as when importing the animations later, the bones must be named correctly when importing animations aswell.

Protip: you can import the mesh of whatever actor your working with on top of the skeleton and it will rig to it automatically, just make sure to uncheck "import skeleton" when importing it.

## Part 2: 32bit Animations
In order to get our animations in to 3DS max, we must convert them using HKXPackUi, however, it only accepts 32bit hkx files.
Converting the animations to 32bit is a simple yet tedious process (If anyone ever finds out how to simplify the process, please let me know.)

Like with creating the skeleton, Click Havok Content Tools along the top of 3DS max and hit “Export”. A new window will pop up
Click File -> Open configuration set and Load the provided custom F4Animation.hko (found at the top of this page)
(Not the one included in the Fallout 4 animation kit, I’ve made my own set)

Select "ConvertAnimation_X32" under Configuration set.
![Select it](/fallout-4/img/convert32.PNG)

now select "Merge Asset" and on the right, you will be able to browse for a file path.
Navigate to where your actor's animations are, which is MESHES/ACTORS/*ActorName*/Animations/ Select the animation you want to convert, copy its name and then click "Open"

now select "Write To Platform" and navigate to where you want to output the 32bit version of the animation. **Do not overwrite the original 64bit one! We'll need it later**
Name what you want to output the 32bit file as, if you copied the name before selecting it, it'll be on your clipboard.

now do this over and over and over and over again until you have all of your desired animations converted to 32bit. If anyone knows a better way to do this, for instance, **one that doesn't require you to do it file by file,** please let me know.

## Part 3: Converting HKX animations to FBX.

This is the easiest part, open up HKXPackGUI and first, and Define out skeleton, select Browse next to the text box where it's asking for the "skeleton.hkx" and select the one you made in Part 1.

Now simply drag and drop all of your 32bit hkx animations in to the big box that says "Drag and drop files here" and hit "Convert HKX to FBX"

![Almost there!](/fallout-4/img/convert32.PNG)

Now all of your animations are in FBX and can be imported in to 3DS max. Make sure to set the scale factor to 1.0 under advanced when importing FBX files.

If you're importing the animations on to a skeleton already in the scene, make sure the bone names are all proper, this is gone over in part 1.

Now that your animations are loading in 3DS max, you can do whatever you want with them.

That's it! I'll be writing a guide later on getting the animations in to Source, so look out for that.
	- Bizz
