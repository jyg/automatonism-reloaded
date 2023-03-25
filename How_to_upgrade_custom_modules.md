## How to upgrade custom modules
If you wrote your own Automatonism modules, according to automatonism-3.1 patterns, this section is for you.
You need iemguts lib to follow those steps.

**IMPORTANT NOTE :** This howto is a bit outdated : relace all instances of '**state_saving_module**' by '**reloaded**' , even in pictures !

### step 1 : create midi learn listeners
* Copy your module in pd/externals/automatonism/patch_editor_abs

(here, we suppose that your module is called "my_module.pd" but you can change this with your real filename).
* Open it with pd >0.50
* Beware that all guis must have send and receive symbols and should not be wired to other objects of the patch (use [receive] objects instead).
* Inside of your module, create a new object : [reloaded/upgrade]

![image](https://user-images.githubusercontent.com/1431894/119808872-d5940280-bee4-11eb-8e6e-1c3f6a910870.png)

This will automatically add some midi_listeners abstractions for every gui of the patch

(before) 

![image](https://user-images.githubusercontent.com/1431894/119808535-80f08780-bee4-11eb-84f1-61a8725128ba.png)

(after)

![image](https://user-images.githubusercontent.com/1431894/119814432-af716100-beea-11eb-851b-379359666811.png)


### step 2 : replace [textfile] objects
* Now, locate the following subpatches : 

![image](https://user-images.githubusercontent.com/1431894/119809281-3f141100-bee5-11eb-8e74-7ac6e0b36bbf.png)

* inside those subpatches, replace every [textfile] instance by [reloaded/textfile $0]

![image](https://user-images.githubusercontent.com/1431894/119809677-a8941f80-bee5-11eb-9eab-74197f290275.png)

This will enable patch-level state-saving support with new savestate object.
 
* save and close your patch

### step 3 : integrate your module into automatonism_menu
Let's update the automatonism "modules" menu entries.  
(Here we assume that your module's name is "my_module").
* First, open an automatonism patch, and search for extra-modules subpatch (using pd find menu).
* Inside the [pd extra-modules] subpatch, add an object [module_create $0 $1 my_module] , save and close the window

![image](https://user-images.githubusercontent.com/1431894/119811171-14c35300-bee7-11eb-8328-b58759cbc51e.png)

* Last step, open the automatonism-modules-menu (by pressing "esc"), and add a bang object to it

![image](https://user-images.githubusercontent.com/1431894/119813412-87353280-bee9-11eb-881f-b90f9bef65d5.png)

with send channel named "$0-create-my_module!"

![image](https://user-images.githubusercontent.com/1431894/119812022-fc076d00-bee7-11eb-864f-77d85e2a4483.png) 

* save and close

