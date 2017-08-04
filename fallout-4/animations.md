## Credits
	Figment - Updated NifTools tools
	ShadeAnimator - Fallout 4 Animation Kit, original guide for importing animations in to max
	Mars - Starting this site and helping with this tutorial.
	Bizz - Figuring out the process for making 32bit skeletons, writing this tutorial.


## Part 1 -  32bit skeleton.


We’ll be using HKXPackUi (located in the animation toolkit)  to convert the animations in to FBX, but in order to do that, we need a 32bit skeleton.hkx file. We do this by starting with the 64bit skeleton.

After deciding what character you want to convert (found in MESHES/ACTORS), find it’s skeleton.hkx file in the CharacterAssets folder.

Drag the skeleton.hkx in to HKXPackGUI and hit HKX <=> XML

![Puush button](/fallout-4/img/hkxpackGUI.png)

The bones have to be in a very specific order. The only way to get the order is taking the 64bit skeleton, so you must take it from the XML.

Look for hkaSkeleton and delete everything that isn't the bone definitions.
Isolate all the bones. Maintaining the order. It's easy to do this using notepad++, as seen here:

{% videoplayer id="myvideo" width="640" height="480" posterExt="png" /vid/isolatebones.mp4{% endvideoplayer %}


Then, at the top of the file, add this:

`
[HAVOK SKELETON DEFINITION FILE]
`
`
[BONES START]
`

At the bottom, add the following:

`
[END]
`

Once you've isolated all the bones, you can save the file as skeleton.txt, or whatever other name you want to give it.

Open up 3DS Max, Import a new file, and now import the skeleton.nif file for your desired actor, this is the same place we found the skeleton.hkx.

With this loaded now, 

Go to Havok Content Tools along the top of 3DS max and hit “Export”. A new window will pop up

Click File -> Open configuration set and Load the provided F4Animation.hko

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

![Scene Explorer](/fallout-4/img/SceneExplorer.png)

Looking at the output log to reference bones that are missing, you’ll see that it says “LThigh” is missing, but in the scene, you have “LTHIGH”. This is because the bone names are case sensitive, so the capitalization must match up. Just select 

`
LTHIGH 
`

and rename it too

`
LThigh
`

Make sure to do this for all misnamed bones. If after correcting all of the bones, but there are still some missing such as camera bones or animobjects, you can simply create a dummy with the name of the missing 
bone. 

You can do this by going to Create>Helpers>Dummy. 

Make sure to link it to the root bone by dragging the dummy under the root bone in the scene explorer. 

Now that we have no more errors about writing the skeleton, select “Write To Platform” in the configuration set, and on the right, input where you want the file to save. Once that’s done, hit 
“Run Configuration” and your 32bit skeleton will be created.

