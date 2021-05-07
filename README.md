# Automatonism [Reloaded]

<p align="left"> <img src="https://raw.githubusercontent.com/jyg/automatonism/master/automatonism_51.png" alt="automatonism_51" ></p>

Based on Automatonism V3.1 from https://www.automatonism.com/the-software.

## New features :

* Midi-mapping and Midi-learn features
* Camomile VST plugin and DAW integration with new objects [playhead] and [macro-control] to enable automation inside DAW
* Automatonism made as an abstaction lib : init a new project just by typing [automatonism] in a blank patch. 
* The new preset and state saving system is based on new savestate object, where preset and state data are stored inside the main patch.
* The legacy file-based preset and state saving system is deprecated, but old savestate structure is automatically imported in new project.
* Ability to save different projects in the same folder with different filenames (no need to use main.pd as filename)
* Several patches can run simultaneously and independently ("local mode" in Preset-Manager)

## To Do :
* Clean all that stuff
* Deeply check camomile integration
* Write tutorial for new features (import old patch ; create new modules ; use as camomile plugin


## Installation :
* Download Automatonism.Reloaded.zip here https://github.com/jyg/automatonism-reloaded/releases
* Unzip it into your puredata - externals folder. You may now have a folder named "automatonism"
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
