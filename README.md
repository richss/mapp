# mapp

This app is currently under development and will eventually be released under an open source license

It serves to map flight data for unmanned and manned aircraft 

it allows the user manipulate parameters that will show where encounters between aircraft occur

additionally metrics relating to the flights are displayed 



****


**screenshots show functionality with different parameters**

spaghettiSoup ; displays entire dictionary worth of manned flights & unmanned flights

![Image description](https://raw.githubusercontent.com/nyetzsche/mapp/master/screenshots/spaghettiSoup.png)




         objects ; 
              uas flight path : pink ; polyline
              uas heat bubble : dark red ; moderately translucent ; circle
                  *(distance around points within uas flight path is equivalent to encounterDistance in feet)
              manned flight path : blue ; polyline
                  *(when an unmanned heat bubble is in contact with any contained points:
                           manned flight path is colored gold )

adsbOne ; displays one individual manned flight and the dictionary of unmanned flights; 

         encounterDistance = 0 feet

![Image description](https://raw.githubusercontent.com/nyetzsche/mapp/master/screenshots/adsbOne.png)

encounterOne ; displays adsbOne with higher distance around unmanned flight locations ; 

         encounterDistance = 3000 feet
   
![Image description](https://raw.githubusercontent.com/nyetzsche/mapp/master/screenshots/encounterOne.png)
   


