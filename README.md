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

## Changes
2021/04/16	-added camomile plugin compatibility

2021/04/01	-added megalon extra-sampler module for Automatonism
	https://github.com/megalon/pd-AUTOMATONISM-sampler
	
## Importing automatonism old patches
* open patch with pd > 0.51
* delete this ...

![image](https://user-images.githubusercontent.com/1431894/119803727-fe65c900-bedf-11eb-93e1-b6b34f58958b.png)

.. and that :

![image](https://user-images.githubusercontent.com/1431894/119803910-2bb27700-bee0-11eb-8577-856ae132d346.png)

* assuming you already installed automatonism(reloaded) in ~/documents/pd/externals/automatonism folder, just type a new box in your patch : 

![image](https://user-images.githubusercontent.com/1431894/119804376-92d02b80-bee0-11eb-8bc0-db737b4dd6df.png)
* this creates the new [declare -paths] and automatonism menu objects

(before)

![image](https://user-images.githubusercontent.com/1431894/119804886-0e31dd00-bee1-11eb-8367-9caaeee29418.png)

(after)

![image](https://user-images.githubusercontent.com/1431894/119805045-315c8c80-bee1-11eb-8ad3-fe97ce025fd7.png)



## How to upgrade custom modules
