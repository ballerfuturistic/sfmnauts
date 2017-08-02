# Understanding Weighting Limitations in the Source Engine
-----

### Source is over a decade old. As such, there are some severe limitations in place compared to modern game engines. One of the worst, especially for a porter, is the engine's limits on bone weights assigned to vertices.

In simple terms, if you throw a mid-high poly model from a recent game into Source, you will absolutely lose rigging data if you don't make some significant changes to the way the model is rigged. How much work you need to do is entirely dependant on how complex the rigging on your model is, and how badly the weight culling is harming pose deforms.


The rigging data loss could be negligable, or it could be completely destructive. It's entirely situational, every rig is different. You may have a high poly model that loses almost no rigging, and then a mid poly model with a nearly broken pelvis.

### This article will explain what causes rigging loss, how to identify it, and how to totally prevent it.
-----

# The Causes

### Failure To Normalize Weight Values

Almost all game engines require vertex weights on a mesh to be **normalized**. What this means is, **for a single vertex, the total combined value of weights assigned to bones must always be exactly equal to 1.0**

Many less experienced users are unaware of this fact. Most 3D programs allow you to create weight values that are **not normalized by default**. Your scene can work just fine without normalization, but when you export your model, **the exporter will silently restructure your weight values to be normalized**. There is no notice of this happening at all.

If you were to export a mesh with non-normalized weight values, then reimport the exported result, you will observe that the weight values have been restructured to be properly normalized.

The consequences of this are usually light since the restructured rigging attempts to resemble what you had before, but **it absolutely can create mismatched results between what you see in your 3D program, and the final rigging you see in-game**. Your rig will survive auto-normalization,  but you can easily lose very crucial weights in delicate areas that really do make a difference up close. When doing custom rigging, **always rig normalized.** Most programs have an option to keep weights normalized at all times while doing your weight assigning.
 

 
### Bone Weights Per Vertex Limit

Source has a hard coded limit on the number of bone weights per vertex. It is integral to the engine and can't be changed.
Most modern engines support 4 weights per vertex, sometimes more. Even many older games have allowed this many.

Source only supports 3. This is a problem, a big problem.

It is _**highly likely**_ the model you just imported was originally rigged with 4 weights per vertex in mind.
What does this mean? It means that any vertices that have more than 3 bone weights are going to drop their lowest weight values until it can come up with a normalized solution that only uses 3 bones at most.

#### _To put it simply, each vertex on the model may only be influenced by up to 3 bones._

You can export **SMD files** with as many vertex weights as you'd like, but if you go past the limit, studiomdl **WILL** restructure your weight values to comply with the limit. Often in ways detrimental to the integrity of the rig.

**DMX files** on the other hand, will simply refuse to compile. (ERROR: ACCESS VIOLATION LMAO)

- SMD and DMX files are able to store weights past the limit, studiomdl is what culls the weights, not the model format
- SMD compiling without any mention of weight culling is the primary reason Source ports are notorious for bad rigging
- In Source 2, the limit is raised to 4, so this problem goes away if by some miracle SFM is ever ported over properly
 

 
### Culling of Normalized Weights With Values Under .050

A well kept secret, Source Engine simply **discards any normalized weights below a value of .05**
This has a huge impact on fine weighting, especially on high poly models where very low weight values are often utilized to keep all those vertices smoothly deforming. Many models you import will have weights below .05, even older games. It may not seem like a big deal, but it is. Depending on how much your model uses low value weights, **this issue all by itself can be severe enough to ruin deforms in very obvious ways, I assure you.** A few dropped weights here and there usually can be ignored, but if you have entire sets of edge loops using low value weights, **there is real potential for serious damage** to your deforms.
