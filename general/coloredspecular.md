       Credit: Kuroyasviel

## Colored Specular

[Sample Files](https://github.com/ballerfuturistic/sfmnauts/raw/master/general/file/colored_specular_guide.zip)

This is applicable for any game that uses colored specular.

THIS IS **NOT** Colored Roughness (Dark Souls 3) or Colored Specular Roughness PBR.


## MODEL:

1. Import the model into 3dsmax

2. Dupicate the model, the original should have the **diffuse** applied while the dupe has the **specular** applied.

3. Export the whole scene as one .SMD

## TEXTURES:

    Typically speculars end in _spec or _s, but if for some reason you can't see the texture names, compare them. 

    Usually the Specular has a very vastly different color scheme from the Diffuse, but if not, they're brighter.

1. Put the colored specular in the **alpha** of the **normal map.**

**(Optional)** Make an exponent out of the colored specular, 
1. Color the **green channel** by 

       255 255 255

2. **(Optional)** Darken the **red channel.** (Experiment with this and just find what you think looks best.)

2. Export as .TGA

## COMPILING:

For the QC, use the one attached to the SFMNAUTS page.

Edit the lines etc.

## MATERIALS:
Once the model is compiled, also use the VMTs in sample files available at SFMNAUTS

As a reminder, **Diffuse VMT** should have no phongboost, and should look exactly like the sample file.

The **Specular VMT** should have phong boost/also look like the sample files, but change parameters to your liking.

## Final
![Final Colored Specular](/img/finalcoloredspecular.png)























