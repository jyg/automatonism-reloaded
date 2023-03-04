# Automatonism [Reloaded]

<p align="left"> <img src="https://raw.githubusercontent.com/jyg/automatonism/master/automatonism_51.png" alt="automatonism_51" ></p>

Fork based on Automatonism V3.1 from https://www.automatonism.com/the-software.

## New features :

* Midi-mapping and Midi-learn features
* Camomile VST plugin and DAW integration with new objects [playhead] and [macro-control] to enable automation inside DAW
* Automatonism made as an abstaction lib : init a new project just by typing [automatonism] in a blank patch. 
* The new preset and state saving system is based on new savestate object, where preset and state data are stored inside the main patch.
* The legacy file-based preset and state saving system is deprecated, but old savestate structure is automatically imported in new project.
* Ability to save different projects in the same folder with different filenames (no need to use main.pd as filename)
* Several patches can run simultaneously and independently ("local mode" in Preset-Manager)

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


## To Do :
* Clean all that stuff
* Deeply check camomile integration
* Write tutorial for new features (import old patch ; create new modules ; use as camomile plugin

	
## Importing Automatonism old patches

* open your Automatonism patch with pd > 0.51
* delete this ...

![image](https://user-images.githubusercontent.com/1431894/119803727-fe65c900-bedf-11eb-93e1-b6b34f58958b.png)

.. and that :

![image](https://user-images.githubusercontent.com/1431894/119803910-2bb27700-bee0-11eb-8577-856ae132d346.png)

* assuming you already installed Automatonism(reloaded) in ~/documents/pd/externals/automatonism folder, just type a new box in your patch : 

![image](https://user-images.githubusercontent.com/1431894/119804376-92d02b80-bee0-11eb-8bc0-db737b4dd6df.png)
* this creates the new [declare -paths] and automatonism menu objects, provided that you installed iemgus external lib

(before)

![image](https://user-images.githubusercontent.com/1431894/119804886-0e31dd00-bee1-11eb-8367-9caaeee29418.png)

(after)

![image](https://user-images.githubusercontent.com/1431894/119805045-315c8c80-bee1-11eb-8ad3-fe97ce025fd7.png)

* save and close your patch, then reopen it.

## How to upgrade custom modules
If you wrote your own Automatonism modules, according to automatonism-3.1 patterns, this section is for you.
You need iemguts lib to follow those steps.

### step 1 : create midi learn listeners
* Copy your module in pd/externals/automatonism/patch_editor_abs

(here, we suppose that your module is called "my_module.pd" but you can change this with your real filename).
* Open it with pd >0.50
* Beware that all guis must have send and receive symbols and should not be wired to other objects of the patch (use [receive] objects instead).
* Inside of your module, create a new object : [state_saving_module/upgrade]

![image](https://user-images.githubusercontent.com/1431894/119808872-d5940280-bee4-11eb-8e6e-1c3f6a910870.png)

This will automatically add some midi_listeners abstractions for every gui of the patch

(before) 

![image](https://user-images.githubusercontent.com/1431894/119808535-80f08780-bee4-11eb-84f1-61a8725128ba.png)

(after)

![image](https://user-images.githubusercontent.com/1431894/119814432-af716100-beea-11eb-851b-379359666811.png)


### step 2 : replace [textfile] objects
* Now, locate the following subpatches : 

![image](https://user-images.githubusercontent.com/1431894/119809281-3f141100-bee5-11eb-8e74-7ac6e0b36bbf.png)

* inside those subpatches, replace every [textfile] instance by [state_saving_module/textfile $0]

![image](https://user-images.githubusercontent.com/1431894/119809677-a8941f80-bee5-11eb-9eab-74197f290275.png)

This will enable patch-level state-saving support with new savestate object.
 
* save and close your patch

### step 3 : integrate your module into automatonism_menu
Let's update the automatonism "modules" menu entries.  
(here we assume that your module's name is "my_module".
* First, open an automatonism patch, and search for extra-modules subpatch (using pd find menu).
* Inside the [pd extra-modules] subpatch, add an object [module_create $0 $1 my_module] , save and close the window

![image](https://user-images.githubusercontent.com/1431894/119811171-14c35300-bee7-11eb-8328-b58759cbc51e.png)

* Last step, open the automatonism-modules-menu (by pressing "esc"), and add a bang object to it

![image](https://user-images.githubusercontent.com/1431894/119813412-87353280-bee9-11eb-881f-b90f9bef65d5.png)

with send channel named "$0-create-my_module!"

![image](https://user-images.githubusercontent.com/1431894/119812022-fc076d00-bee7-11eb-864f-77d85e2a4483.png) 

* save and close

