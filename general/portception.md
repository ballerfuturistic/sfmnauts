### DO NOT PORT A PORT.

It may seem tempting to use a preexisting port as the basis for your project. This is a bad idea for many reasons, with the most obvious being that some authors (especially from obscure platforms like MMD/XNALARA) are very protective of their own work and will be quick to go after you and demand credit or removal.

Additionally, keep in mind this is a hobbyist community. The majority of porters are generally inexperienced with 3D concepts, often knowing only enough to port to their platform of choice, breaking all kinds of things in the process.

It's simply bad practice; don't rely on other people to do your work for you. The best way to improve your skills and get better at what you do is to learn how to do things yourself. Apply your own methods and expand on them in future endeavors.
Practice makes perfect.

**It is incredibly important that you begin your project with a fresh extraction from the game files whenever possible, only utilizing others' work as a last resort for complicated issues where it does not make sense to invest a large amount of time into something when someone else has already done so.**

Examples of situations where using others' work could be justifiable:

* Requiring portions of a mesh to be rebuilt due to import issues
* Requiring significantly altered UV maps or texture layouts in order to achieve the correct result when ported
* Utilizing _necessary_ texture edits, such as ambient occlusion removal or eye texture conversion

In the case of extensive rigging or bone loss, it is **HIGHLY INADVISABLE** to rely on others' work to rectify the situation.
Poor rigging is by far the biggest common issue shared amongst inexperienced hobbyist users. It's not always the case of course, but more likely than not, you are going to end up importing garbage rigging.
Bad rigging is not better than no rigging at all, they are equally unacceptable.

Even if you have no intention of making your own models one day, learn how to properly rig. A model is worthless without a good rig to pose it. Even if your model imports with perfect game accurate rigging, it is highly likely that it won't translate that way to Source or other older engines, due to weighting limitations. Please read Taco's guide on Source Engine rigging for more information on this.

### COMMON ISSUES WITH PORTS FROM OTHER PLATFORMS:

Most ports you find for other platforms will be damaged in some way from their original extracted state, unknowingly by the author.

XNA and Gmod users in particular tend to only understand 3D concepts directly relating to porting to their platform, often breaking or ignoring glaring problems in favor of quick results. You are much more likely to find quality work from authors who work with professional game engines such as Unreal or Unity.

**XNALARA:**
* Bone rotations are not supported, animations will never be compatible
* Completely renamed bones
* Altered skeleton hierarchy
* Textures are often modified from their original incarnation, especially specular maps
* Damaged mesh data, rigging, and smoothing errors, due to author inexperience
* DeviantArt community, so don't expect quality work in general

**Garry's Mod:**
* Bones renamed to Valve Biped format, but usually the old HL2 format
* Finger bone rolls changed, rest position modified into a claw state
* Double compression on textures, **DO NOT** extract from a VTF texture with DXT compression
* Facial bones are often removed in favor of vertex flexing
* Rigging loss due to Source's weighting limitations (SFM is no different!)
* Possibly reduced bone count due to Gmod being an older engine branch
* Damaged mesh data, rigging, and smoothing errors, due to author inexperience
* Semi DeviantArt community, extremely varying levels of quality

**MMD (MikuMikuDance):**
* Skeletons are completely replaced, model is rerigged to the dancing anime girl skeleton
* Excessive material reassignment
* Textures are often modified from their original incarnation, especially specular maps
* DeviantArt/Weaboo community, although surprisingly they often produce much higher quality work than XNA users

**KCMM (Brawl Vault):**

_A place where you may find models nobody else seems to know how to extract, occasionally useful_

* Skeletons are completely replaced, model is usually rigged to an existing character's skeleton
* Meshes are often reduced from their initial polycount to be optimized for the Wii
* Downscaled texture sizes
* Somewhat experienced community, but also rather whiny, and dead
  * Gamebanana hosts content for Smash 4, many former users reside there currently

**The Models Resource:**

_Often a good source to acquire unmodified, cleanly extracted models when you don't have the tools you need_

* Rigging may or may not be included, if it is, it's usually the original unmodified bones and weighting
* Original textures and material names are usually maintained
* Still subject to any errors caused by the import tools, most users won't fix them before uploading
  * Usually safe from any added errors caused by inexperienced users, due to very little modification from initial imports

**Second Life:**

_Do not ever use anything from Second Life, under any situation_

_Guaranteed garbage quality and an insane community obsessed with copyright_
