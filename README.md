# Ommetpp SAC dockerfiles
Custom Omnetpp docker container built for SAC course @ UniMore.

## How-to
Launch `./omnetpp-gui/build` to build Docker image. 
To execute omnetpp, please launch `~/omnetpp/run` and execute `omnetpp` command into the shell.

**Remember to choose /root/models folder as default Workspace!**

Are available various samples in the `./omnetpp/samples` host folder; feel free to use it. Just use debug mode when building it.
Other stuff is useless at the moment.

## Notes
Source files for building OMNeT++ related docker images

 - omnetpp-base -> ubuntu based image containing all required packages to build and use OMNeT++ on the command line (clang compiler, make etc.)
   - omnetpp -> contains a pre-built OMNeT++ distribution for quickly compiling and running a model in Cmdenv (No IDE or Qtenv support!)
     - inet -> OMNeT++ and INET in the same image (release only) to be used as a base image for INET dependent models
   - omnetpp-gui -> contains a pre-built OMNeT++ with all GUI tools (except OSG and osgEarth), that can be accessed using X from the host
     - inet-gui -> Same as inet, except based on omnetpp-gui, so it has IDE and Qtenv support
 - swarm-base -> tools and packages required to run OMNeT++ simulations in a docker swarm (distcc, compiler, OMNeT++ core)
 - ci-base -> an image containing Linux, Windows and macOS compiled versions of OMNeT++ (for continuous integration)
   - ci-inet -> an image used to run continuous integration test for INET (contains NSC, ffmpeg and other optional INET dependnecies)
 - docker-sphinx -> Sphinx docker image for building OMNeT++ and INET documentation projects
