# **OUTDATED**

**I don't maintain this repo anymore but leave it here as a reference.**

Needed settings for using my i3 fork with KDE patches (https://github.com/sLite/i3) are found directly in the README.md of the i3 repository

# i3-config

The i3 configuration that i use with KDE 4

I use i3 with KDE 4, have a dualscreen setup at both home and work, but with different xrandr output names in both places. This is how i deal with that and how i start i3 instead of KWM.


## Config generation

I dont edit .i3/config directly (that's why it is on gitignore), it gets concatenated from different parts when i3 gets started.

It gets assembled from 3 files:

* config-$I3_CONFIG-pre
* config-shared
* config-$I3_CONFIG-post

The only thing you need is an additional file in your .i3 directory on each computer named

* i3-config-name (also on gitignore)

with the following content

	export I3_CONFIG=home

This is how you choose which -pre and -post files are added to the config-shared.


## Important Files

### ~/bin/i3startup

The command i use for starting i3, that way i can control commandline options and do additional tasks.
This also assembles the config depending on I3_CONFIG before running i3.
This needs to be in the path, i use the bin directory in my home for doing that.

### .kde4/env/wm.sh or .config/plasma-workspace/env/wm.sh

This tells KDE/Plasma to start our script instead of kwm.
Starting with Plasma 5 the file moved to .config instead of .kde4


## Additional Notes

### Session Saving

I have disabled session saving in KDE and always start with an empty session.
Everything i need is started by i3.

