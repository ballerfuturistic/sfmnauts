## Credits
	MetamorpheSTLK - Original guide written in french
	Jeff Belinger - English Translation
	Bizz - Formatting

#### What is Sub-Surface Scattering?

SubSurface Scattering, or, SSS is a procedure of light transfer that makes rays of light penetrate the surface of an object. As it makes contact with matter, it diffuses and escapes in multiple points

It is a transparency phenomenon that you can see when you put your hand in front of a light source

Here’s a step by step tutorial explaining how to realize this effect under source engine by using a lightwarp texture and phong.

Open Photoshop and make a new document called “gradient skin” with width 256px and height of 16px

You now have a blank document

Select the gradient tool and reproduce this gradient as much as possible

![Sorry for small image](/general/img/sss_gradient.png)

Trace the gradient from left to right on the blank canvas

Go in “image”, then “setting” and then “tint and saturation”
Put the saturation at -20 and luminosity at -50

Save your file as a .TGA file with the name “texture_lightwarp” in “24bits”

open the TGA with VTFEdit

click “Clamp S”, “Clamp T” and “No Mipmap” in the VTF options and save it, this is your lightwarp texture.

In order to apply it to the material, add the material paramater "$lightwarptexture"	"path/to/lightwarp"

Next, add some Phong shaders to your material to make it look more like skin

Here's a reference Material

	"VertexLitGeneric"
	{
		"$basetexture" "texture_d"
		"$bumpmap" "texture_n"

		"$phong"	"1"
		"$phongexponent"	"4"
		"$phongboost"	"1"
		"$phongtint"	"[.85 .85 1]"
		"$halflambert"	"1"
		"$phongalbedotint"	"1"

		"$lightwarptexture"	"path/to/lightwarp"
	}

You'll want to play around with the phong and lightwarp a bit until it looks good, but it's really rather simple.
