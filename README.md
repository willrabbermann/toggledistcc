# toggledistcc #
```toggledistcc``` does the following:

1. Set ```MAKEOPTS=``` automatically to toggle distcc opts. 
   Currently sets "-j#DISTCC_TJ -l#LOCAL_TJ" but no other makeopt setting will be saved. (TODO)

2. Set ```FEATURES=``` and preserves previous feature entries, as well as performing 
   space limiting (one space per word, none on the beginning or ends).

3. Start/stop distcc service in an OpenRC init environment.

## config.h ##
User configuations are set in ```config.h``` before compiling.

toggledistcc is compiled with a constant ```DISTCC_TJ```, which represents the max number of threads when using distcc (remote + local); It is recommended to update this to match your setup.

A system command is run to find the thread count of your local processor. Therefore it is not necessary to update ```LOCAL_TJ```.

# why? #
I made this program so I could easily turn distcc off when I start getting ICE (internal compiler errors).
Some things compile fine with distcc opts but its useful being able to turn them off when errors arise.


