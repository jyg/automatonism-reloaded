# Automatonism [Reloaded]  v 4.2.4
![image](https://user-images.githubusercontent.com/1431894/227710524-edfb046d-e393-48c3-a578-8040f372e282.png)

**Automatonism [Reloaded] v 4.x** is a fork based on Automatonism V3.1 from https://www.automatonism.com/the-software.
The aim is to upgrade Automatonism and use it as a live instrument, with, for example, enhanced midi mapping. 
## New features :

* **Plugdata compatible** (for standalone or as DAW plugin)
* **Midi-mapping and Midi-learn features**
* DAW integration with new objects [playhead] and [macro-control] to enable automation inside DAW
* Automatonism made as an abstraction lib : init a new project just by typing [automatonism] in a blank patch. (see next section) 
* The preset and state saving system is based on **'savestate' object**, where preset and state data are stored inside the main patch.
* The legacy file-based preset and state saving system is deprecated, but old savestate structure should be automatically imported.
* Ability to save different projects in the same folder with different filenames (no need to use main.pd as filename)
* **Several projects can run simultaneously and independently** ("local mode" in Preset-Manager)
* camomile plugin support is no longer supported, as  **Statesaving into DAW is broken for camomile plugin version** .
* Unlike original project, **Automatonism [Reloaded]** intensively uses internal abstractions inside modules, in order to add new features.
  
## Installation / Getting Started (puredata + iemguts) :

https://github.com/user-attachments/assets/44abf3ae-7677-484c-8b54-1686f1995bb4

* Automatonism [Reloaded] is accessible via Deken menu in puredata (Tools -> Install Externals).
You can also downloads installation files (.dek) from this github repository. Search in Releases section.
* If you have iemguts lib installed with puredata, you can directly open a new patch, create an object box (ctrl/cmd+1) and type [automatonism]. This will create the automatonism object and add declare paths.
* Alternatively, or with pd vanilla, you can open the included _main_patch(template).pd and save it anywhere with a new name.
* Start patching.
  
## Installation / Getting Started (plugdata) :

https://github.com/user-attachments/assets/9070dab4-3ed0-4b2e-ac11-0ea293900d1c

* With plugdata, type [automatonism] as new object in a blank patch. If you encounter crash, you must type [automatonism $0]  (with $0 argument) instead of [automatonism]
* Start patching.

## Software Requirements
* **pd** >= 0.55
* external lib **iemguts** needed for enhanced editing features, but not mandatory.

**or**

* **plugdata** > 0.9.2
  
## Midi Learn

https://github.com/user-attachments/assets/79cb93f1-f540-49b9-ba61-427bb3f21344

(How to enable midi mapping with midi learn function, how to change mapping range, and how to cancel a midi-mapping)

## DAW integration - automation of parameters with 'macro-control' module (plugdata)

https://github.com/user-attachments/assets/6ae4750e-c7a6-42be-8f6c-24e50f5b9f2b

Instead of mapping a parameter to a real midi controller, you can map it to a slider of a [macro-control] module. This way, you can connect it to a parameter curve in the DAW and record automations in a track. 

See https://plugdata.org/docs/book/DAWIntegration.html for other infos about DAW integration of plugdata.

## Changes
2025/05/04	-updated doc (this file)

2023/11/15	-improved Plugdata support, added patch statesaving inside DAW

2023/03/25	-rewrite for plugdata support

2021/04/16	-added camomile plugin compatibility

2021/04/01	-added megalon extra-sampler module for Automatonism
	https://github.com/megalon/pd-AUTOMATONISM-sampler


## To Do :
* Clean all that stuff, especially everything that is related to daw-storage ([savestate] does the job)
* Remove camomile-related files and stuff
* Write tutorial for new features (import old patch ; create new modules)
  
## How_to_import_old_patches

https://github.com/jyg/automatonism-reloaded/blob/master/How_to_import_old_patches.md

## How_to_upgrade_custom_modules

https://github.com/jyg/automatonism-reloaded/blob/master/How_to_upgrade_custom_modules.md
