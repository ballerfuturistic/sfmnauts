## Credits

Method: **Ninja Nub**, **Kuroyasviel**

## Notes

The textures follow the standard filenames: **wpn\_ak\_74** and **wpn\_ak\_74\_bump**

**wpn\_ak\_74 **is obviously the **Diffuse**

Information below pertains to **\_bump **files.

so.. **filename** and **filename\_bump**

## Channels

Open your **\_bump**.

**Green channel** holds the Specular.

Run the whole **\_bump** through [**NJOB**](http://charles.hollemeersch.net/njob/), then load the normal map that was generated. .

Put the **Specular** in the **Alpha of the normal map.**

**This is your finished Normal Map, export as your Normal.**

Now for your** Exponent.**

Make a copy of the **Specular**, and then run these curves\(control+m\) on the **copy** of the **Specular**

```
Output   Input
7        93
31       147
125      212
```

Make a new layer and brush the whole layer as **128, 128, 128**, then put the** Curved Specular** into the **red channel of THIS newly created layer.**

**This is your finished exponent, export as your Exponent.**

We now have Diffuse, Normal, Exponent, and Specular in the alpha of your Normal Map.

