# Automatonism [Reloaded]  v 4.0-pre4
![image](https://user-images.githubusercontent.com/1431894/227710524-edfb046d-e393-48c3-a578-8040f372e282.png)

![image](https://github.com/jyg/automatonism-reloaded/assets/1431894/dbda805b-cfa4-4a82-afad-e6f6d56dfc26)

**Automatonism [Reloaded] v 4.x** is a fork based on Automatonism V3.1 from https://www.automatonism.com/the-software.

The aim is to upgrade Automatonism and use it as a live instrument, with, for example, enhanced midi mapping. 

Unlike original project, **Automatonism [Reloaded]** intensively uses internal abstractions inside modules, in order to add new features.
## New features :

* New ! **Plugdata compatible** (for standalone or as DAW plugin)
* improved state saving inside DAW (with plugdata latest nightly build)
* **Midi-mapping and Midi-learn features**
* DAW integration with new objects [playhead] and [macro-control] to enable automation inside DAW
* Automatonism made as an abstraction lib : init a new project just by typing [automatonism] in a blank patch. (requirements : Pd + iemguts, or Plugdata >0.8.1) 
* **The new preset and state saving system is based on** (not-so-) new **'savestate' object**, where preset and state data are stored inside the main patch.
* The legacy file-based preset and state saving system is deprecated, but old savestate structure is automatically imported in new project.
* Ability to save different projects in the same folder with different filenames (no need to use main.pd as filename)
* **Several projects can run simultaneously and independently** ("local mode" in Preset-Manager)
* experimental palette feature for pd vanilla + iemguts. See here : [palette/README.md](https://github.com/jyg/automatonism-reloaded/tree/master/palette/README.md)
  
## Installation :
* Automatonism [Reloaded] should now be accessible via Deken menu in puredata (Help -> Find Externals). Latest version : v4.0-pre4.
* You can also download Automatonism.Reloaded.zip here  https://github.com/jyg/automatonism-reloaded/archive/refs/heads/master.zip. Unzip it into your puredata - externals folder. You may now have a folder named "automatonism"
* For camomile plugin versions, see here : https://github.com/jyg/automatonism-reloaded/releases. **Statesaving into DAW is currently broken for camomile plugin version**.
* If you have iemguts lib installed with puredata, you can directly open a new patch, create an object box (ctrl/cmd+1) and type [automatonism]. This will create the automatonism object and add declare paths.
* Alternatively, you can open the included template-patch _main_patch(template).pd and save it anywhere with a new name.
* Start patching.

## Software Requirements
* **pd** >= 0.54
* external lib **iemguts** needed for enhanced editing features, but not mandatory.

**or**

* **plugdata** > 0.8.1 (currently nightly build)

## Changes

2023/11/15	-improved Plugdata support, added patch statesaving inside DAW

2023/03/25	-rewrite for plugdata support

2021/04/16	-added camomile plugin compatibility

2021/04/01	-added megalon extra-sampler module for Automatonism
	https://github.com/megalon/pd-AUTOMATONISM-sampler


## To Do :
* Clean all that stuff
* Deeply check camomile integration
* Write tutorial for new features (import old patch ; create new modules ; use as camomile plugin

## How_to_import_old_patches

https://github.com/jyg/automatonism-reloaded/blob/master/How_to_import_old_patches.md

## How_to_upgrade_custom_modules

https://github.com/jyg/automatonism-reloaded/blob/master/How_to_upgrade_custom_modules.md
