# Client differences between Pre-WoD and Post-WoD

The biggest difference between MoP and WoD/Legion clients is the filesystem. MPQ archives include listfiles, but CASCv2 filesystem doesn't contain a listfile, which means that you need to constantly fetch or generate a new listfile when a new patch drops and want to extract something.  

Another change introduced in WoD is how the game handles new models and the textures.

Also Legion introduced very heavy changes to WMOs and M2s (chunking them). Thankfully WMV and M2ModRedux are compatible with the currently latest version of WoW client, which at the time of writing this guide is 7.2.5.

Even when there are differences between expansions, I **strongly encourage you to experiment and try out old and obsolete tools**. It might crash with some files or just spit out a mess, but sometimes you hit a jackpot and end up with a model that just needs small fixes or just requires textures to be applied.
