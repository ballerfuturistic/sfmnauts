## Credits

Method: **Blueflytrap**, **Sundownsyndrome**

Simplification: **Kuroyasviel**

## Channels

R - Specular

G - Roughness

B - Useless

Make specular and roughness their own layers.

Paste specular and roughness into each channel of itself to make it darker.

Flip green channel of normal map.

**Specular**

Images &gt; Adjustments &gt; Exposure

Exposure to 0.4545

Make **3 specular** layers.

Make **4 roughness** layers.

**\[DIALELECTRIC SPECULAR\]**

Invert one over a roughness and apply the dialectric curve to it, copy green channel into the alpha of normal map

**\[METAL SPECULAR/NALT\]**

Set specular to multiply, put 180 into left levels for roughness

Import as A8 with VTFEdit

**\[EXPONENT\]**

Apply Diaelectric curve to roughness, paint Green and Blue channel to 128x3

Duplicate the layers and paint the Green and Blue channels to 253x3

Put specular into alpha mask of duplicated layer.

Make sure the 128 layer is under the 235 layer.

**\[Diffuse\]**

Roughness right output box to 100

Specular invert and then multiply it over roughness.

Merge, then put the green channel into diffuses alpha and invert.

Import Diffuse, normal, Exponent as BGRA8888

