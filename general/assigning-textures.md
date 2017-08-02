
# Assigning textures in your 3D Program
-----

When you import your model, usually you will not immedietly see the textures assigned.

If your file is an .obj with a .mtl in the same location, your program should automatically assign the textures to the model assuming the texture files are where the .mtl expects them to be. Otherwise you will have to assign them manually.


## 3DS Max

### Importing an .obj with a proper .mtl:

1. Check **Show maps in viewport** while viewing **OBJ Import Options** before importing
2. Textures should automatically be assigned and visible in the viewport

pic

### Redirecting existing texture paths:

1. After importing your model, **save the scene**
2. Press **Shift+T** to open the **Asset Tracking** window, here you will see any texture paths set prior
3. For each line, right click and select **Set Path**, this opens the **Specify Asset Path** window
4. Use the navigation window to set the path to the new location of the texture its referencing
5. The viewport should now show the textures on the model once the new path has been set

pic

### Assigning textures manually:

1. **Open the Slate Material Editor (M)** and scroll down until you find **Scene Materials**
2. The model's materials are located here, double click the one you want to assign a texture to
3. The **Material Node Editor** will appear in the view window, locate the box for a material
4. Attached to the **Diffuse Color property** for your material, there should be a node labeled **Bitmap**, if not, create it
5. **Double click the Bitmap node** and the map window will appear, expand the **Bitmap Parameters** section
6. Click the first option, a window will appear for you to browse to the location of the texture file to assign
7. Right click the Bipmap node, checkmark **Show Shaded Material in Viewport**
8. Repeat this process for each texture you need to assign

pic

### Enabling translucency in the viewport:

1. At the top left of your active viewport, **click the third option**, your shading settings
2. In the window that appears, **hover over Materials**, then checkmark **Enable Translucency**

pic

# Blender

### Assigning textures in 3DSMax assuming your model tells you what textures are missing.
