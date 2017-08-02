# Understanding Weighting Limitations in the Source Engine
-----

### Source is over a decade old. As such, there are some severe limitations in place compared to modern game engines. One of the worst, especially for a porter, is the engine's limits on bone weights assigned to vertices.

In simple terms, if you throw a mid-high poly model from a recent game into Source, you will absolutely lose rigging data if you don't make some significant changes to the way the model is rigged. How much work you need to do is entirely dependant on how complex the rigging on your model is, and how badly the weight culling is harming pose deforms.


The rigging data loss could be negligable, or it could be completely destructive. It's entirely situational, every rig is different. You may have a high poly model that loses almost no rigging, and then a mid poly model with a nearly broken pelvis.

### In this article I will explain what causes rigging loss, how to identify it, and how to prevent it.
-----

# The Causes

### Bone Weights Per Vertex Limit

Source has a hard coded limit on the number of bone weights per vertex. It is integral to the engine and cannot be changed.
Most modern engines support 4 weights per vertex, sometimes more. Even many older games have allowed this many.

Source only supports 3. This is a problem, a big problem.

It is _**highly likely**_ the model you just imported was originally rigged with 4 weights per vertex in mind.
What does this mean? It means that any vertices that have more than 3 bone weights are going to drop their lowest weight values until it can come up with a normalized value that only uses 3 bones at most.

#### _To put it simply, each vertex on the model may only be influenced by up to 3 bones._

You can export **SMD files** with as many vertex weights as you'd like, but if you go past the limit, studiomdl **WILL** change your weight values to comply with the limit. Often in ways detrimental to the integrity of the rig.

**DMX files** on the other hand, will simply refuse to compile. (ERROR: ACCESS VIOLATION LMAO)

- Note that both formats are able to contain weights past the limit, it is only on compile when the culling will occur.
