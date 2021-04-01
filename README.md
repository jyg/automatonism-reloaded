# automatonism_2021

<p align="left"> <img src="https://raw.githubusercontent.com/jyg/automatonism/master/automatonism_51.png" alt="automatonism_51" ></p>

Based on Automatonism V3.1 from https://www.automatonism.com/the-software
Legacy preset and state saving file system is deprecated. 
New preset and state saving system is based on new savestate object.

## New features :

* automatonism made as an abstaction lib : init a new project just by typing [automatonism] in a blank patch.
* local patch state saving
* presets saved inside the main patch
* automatic import of old savestate structure
* ability to save different projects in the same folder with different filenames (no need to use main.pd as filename)
* midi-mapping enabled and midi-learn feature

## Installation :
* Copy  automatonism folder into your puredata - externals folder.
* In a black patch, type [automatonism].
* start patching.

## Software Requirements
* pd >= 0.51
* external lib iemguts needed for enhanced editing features, but not mandatory.


## changes
2021/04/01
-added megalon extra-sampler module for Automatonism
	https://github.com/megalon/pd-AUTOMATONISM-sampler
