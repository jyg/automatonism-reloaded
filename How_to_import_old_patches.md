## How to Import Automatonism old patches

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
