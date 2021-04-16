# Automatonism Reloaded

<p align="left"> <img src="https://raw.githubusercontent.com/jyg/automatonism/master/automatonism_51.png" alt="automatonism_51" ></p>

Based on Automatonism V3.1 from https://www.automatonism.com/the-software.

## New features :

* automatonism made as an abstaction lib : init a new project just by typing [automatonism] in a blank patch.
* The legacy file-based preset and state saving system is deprecated, but old savestate structure is automatically imported in new project. 
* The new preset and state saving system is based on new savestate object, where preset and state data are stored inside the main patch.
* ability to save different projects in the same folder with different filenames (no need to use main.pd as filename)
* midi-mapping enabled and midi-learn feature
* possibility of running several patches simultaneously and independently
* Camomile VST plugin and DAW integration with new objects [playhead] and [macro-control] to enable automation inside DAW

## To Do :
* clean all that stuff
* deeply check camomile integration
* write tutorial for new features (import old patch ; create new modules ; use as camomile plugin


## Installation :
* Download https://github.com/jyg/automatonism/archive/refs/heads/master.zip
* Unzip it into your puredata - externals folder and rename 'automatonism-master' folder as 'automatonism'
* If you have iemguts lib installed with puredata, you can directly open a new patch, create an object box (ctrl/cmd+1) and type [automatonism]. This will create the automatonism_menu object and add declare paths.
* Alternatively, you can open automatonism/main.pd as a template and save it anywhere with a new name.
* start patching.

## Software Requirements
* pd >= 0.51
* external lib iemguts needed for enhanced editing features, but not mandatory.


## changes
2021/04/16	-added camomile plugin compatibility

2021/04/01	-added megalon extra-sampler module for Automatonism
	https://github.com/megalon/pd-AUTOMATONISM-sampler
