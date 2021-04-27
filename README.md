# R_environ_afni


AFNI's group level scripts (e.g., 3dLMEr, 3dMSS) will require you install specific R packages. 
If your working on a cluster (e.g., longleaf), you'll want to make sure your script references the exact versions and packages you need for your project.

First, create a local lib in terminal (EXAMPLE below-edit these to make your specific needs):

> mkdir -p ~/R/libs
> echo 'R_LIBS_USER="~/R/libs"' >  $HOME/.Renviron 

#this makes sure this is pulled up as your R environ. I add this to beginning of each script to make sure.

If you ever need to add new one packages to R environ, open an OneDemand R session in the correct version you want to work in (for afni, typically 3.6.0, but keep up to date with this by going to afni page for that package).

*install.packages("packagename", lib="~/R/libs")* #change this to whatever lib you want.

In script, so R doesn't crash out, include:

*export R_MAX_VSIZE=32000000000*


*module load afni/20.3.00* (or whichever version you may need in the future)#makes sure script is loading proper version


*module load r/3.6.0* (or whichever version you may need in the future) #makes sure script is loading proper version

