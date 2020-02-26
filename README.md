# mapp

This app is currently under development and will eventually be released under an open source license

It serves to map flight data for unmanned and manned aircraft 

it allows the user manipulate parameters that will show where encounters between aircraft occur

additionally metrics relating to the flights are displayed 



****

**screenshots show functionality with different parameters**

****

**spaghettiSoup.png** ; 
displays entire dictionary worth of manned flights & unmanned flights

![Image description](https://raw.githubusercontent.com/nyetzsche/mapp/master/screenshots/spaghettiSoup.png)




         objects ; 
              uas flight path : pink ; polyline
              uas heat bubble : dark red ; moderately translucent ; circle
                  *(distance around points within uas flight path is equivalent to encounterDistance in feet)
              manned flight path : blue ; polyline
                  *(when an unmanned heat bubble is in contact with any contained points:
                           manned flight path is colored gold )

**adsbOne.png** ; 
displays one individual manned flight and the dictionary of unmanned flights; 

         encounterDistance = 0 feet

![Image description](https://raw.githubusercontent.com/nyetzsche/mapp/master/screenshots/adsbOne.png)

**encounterOne.png** ; 
displays adsbOne with higher distance around unmanned flight locations ; 

         encounterDistance = 3000 feet
   
![Image description](https://raw.githubusercontent.com/nyetzsche/mapp/master/screenshots/encounterOne.png)
   
**dablaanc.png**

geojson of FAA LAANC authorization grid overlaid with display of manned & unmanned flights ;

         encounterDistance = 1000

   
![Image description](https://raw.githubusercontent.com/nyetzsche/mapp/master/screenshots/dablaanc.png)


code for geojson import below 

         from ipyleaflet import Map, GeoJSON
         import json
         import os
         import requests

         if not os.path.exists('30b525681586478f8b6549985f23c40b_0.geojson'):
             url = 'https://opendata.arcgis.com/datasets/30b525681586478f8b6549985f23c40b_0.geojson'
             r = requests.get(url)
             with open('30b525681586478f8b6549985f23c40b_0.geojson', 'w') as f:
                 f.write(r.content.decode("utf-8"))

         with open('30b525681586478f8b6549985f23c40b_0.geojson', 'r') as f:
             data = json.load(f)


         geo_json = GeoJSON(data=data, style = {'color': 'green', 'opacity':1, 'weight':1.9, 'dashArray':'9', 'fillOpacity':0.1})
         
         mapp.mapp.add_layer(geo_json)
