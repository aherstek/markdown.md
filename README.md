# andie's technical activity log 2024
# my personal time log for geom99 group 4: https://docs.google.com/spreadsheets/d/1UeDhiMlVg55BBoP2paiI3WA6aODq5btSCYPUxrXSli0/edit?usp=sharing

_**february 29th:** setting up markdown.md doc in github and learning md syntax from here: https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax_.

**march 1:**
**week7/8 checklist notes and timeline**
* :alarm_clock: 8am: Started my own ArcGIS Server on Google Cloud Platform. Followed Shawn's instructions (https://youtu.be/dyFeyBX9jIY) to get everything up and running. NOTE: document all passwords / IP addresses / important information Shawn addresses in the video in Notepad, as some information is only shown to you once and it is helpful to have it all safely stored.
* :alarm_clock: 9am: VM up and running. REMEMBER to turn off VM when not using! You can ensure that everything is turned off my seeing a "stop" icon on GCP and shutting down VM from start menu.
* :alarm_clock: 1115am: Contiued to work through checklist steps - publishing on GCP VM into ArcGIS Server (Canada.shp used from prior weeks).
* :alarm_clock: 435pm: Completed checklist. Overall it was a bit challenging - ESRI documentation and Shawn's notes/videos were helpful when stuck.

 _**brief step by step process of set up**_
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/3928caeb-f655-416a-8647-813917fda204)
 * :thumbsup: Logging into GCP
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/c17a41a7-e98e-4035-a45f-08940caf47cc)
 * :thumbsup: Enabling this API
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/c788b8b0-bac1-405e-8779-a8340feadad5)
 * :thumbsup: Clicking "Create Instance"
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/fa97ee29-2dfe-401e-8220-1199be18b45e)
 * :thumbsup: Configuring instance settings. We learn about the cost to run such instance on an hourly and monthly basis (kinda cool!)
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/aa737fe4-2744-4ea7-a6f5-7949b072eee5)
 * :thumbsup: Continuing to set up instance...
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/ba2da5c4-3a38-4238-944b-c84059b62808)
 * :thumbsup: Linking to Shawn's provided image for us to use (custom image in boot disk settings)
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/e45dc1b1-d455-405b-b1e1-2e3d0523eb4f)
 * :thumbsup: Once complete, we see changes in cost estimate
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/24ae63ec-c2db-4ffa-b953-669e43ae96a8)
 * :thumbsup: Setting up firewall
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/c07c4116-c713-46ec-9160-0dcfb6eba702)
 * :thumbsup: Starting up our instance! Note: It may take a few minutes (just like starting up your own computer in the morning)
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/c24b7e60-1332-4539-bf47-7689483fb33f)
 * :thumbsup: Creating our firewall rule, with direction of traffic: Ingress and action on match: allow. Targets: All instances in the network, IP4V ranges (unrestricted: 0.0.0.0/0), specify port TCP 444 then click **Create**
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/3383b265-ce11-42fa-a5b4-a473eba18f43)
 * :thumbsup: Checking back on our VM - it's running!!! 😸
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/07241d0b-85c9-474f-ae51-b61f13cf5470)
 * :thumbsup: Configuring windows account, click **Set**. Password will then be provided, write it down as it won't be easy to remember! Also, take note of internal / external IP addresses provided on the VM instance screen. They will be needed later!
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/7ed700dc-2e56-4009-a73c-a403b13097a0)
 * :thumbsup: Go to your computers start menu and find Remote Desktop - log in with credentials Shawn provides (external IP needed as stated prior). A "risk" pop up will show, click **Yes**. We will then connect to the remote desktop.
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/915ed565-6ebb-4cfc-bcff-62e24f22f559)
 * :thumbsup: Remote desktop will look like this. We are now ready to proceed.
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/09c1c1c7-ec0a-4fbc-abea-3faa5f075603)
 * :thumbsup: **try** input your IP used above into google - you should see image above. if you put https:// infront - you will get _"connection is not private"_ (its normal! dont worry). click advanced and proceed. now add to your url (https://IP address /arcgis/rest/services) and experiment with the manager too at arcgis/manager by logging in from Shawn's instructions.
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/6db6f915-9f20-45b4-9146-2c937a0d1f8e)
 * :thumbsup: example of server manager screen
 * :thumbsup: we are now ready to proceed ! :smile:
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/91400e87-ee01-40b0-84f5-6b0caee32e75)
 * :thumbsup: when shutting down server --> 3 dots, **stop** and wait until status icon is grey.

* :thumbsup: at this point I forgot to keep taking screenshots so it will be texted based from now on.
* :thumbsup: **DuckDNS (https://www.duckdns.org/) to establish new domain**
* Complete reCaptcha verification on the DuckDNS website to generate a domain. You will input the External IP from GC Console into the designated field and click to update. The resulting domain will be: your_info.duckdns.org. Following any interruptions in the Google Cloud VM, subsequent reboots will automatically regenerate the external IP. This IP, associated with the new domain, can be seamlessly updated within DuckDNS without requiring modifications in server settings or other relevant areas where VM usage is integral.
* :thumbsup: **SSL cert**
* Spark up your VM and update your IP (external) to your DuckDNS. Log into your remote desktop and open IIS Manager (it's a desktop app, search ISS). Default website is bindings. Select 443 port, edit and define domain to match your DuckDNS. Then, use https://www.win-acme.com/ and download. Run wacs.exe, click more info, run anyway. You will then set your options via code displayed on screen. Create your cert, all bindings, confirm, open T.O.S, agrree, provide your email and close window when code is done. Make sure it worked on DNS url, and you will be gvem SSL certificate viewable in your internet browser.
* :thumbsup:**publishing to AGOL**
* Sparking up your VM instance on GCP (click _Start/Resume_) and copy your external IP, go to your DuckDNS and update domain. Go to ArcGIS Rest Endpoint to check server response / it's working (log in as admin). Log into your remote desktop, and copy Canada data with the same path. In ArcGIS Pro, add new ArcGIS Server Connection. Server URL will be your DNS URL with port :6443/arcgis. Then, once logged in with siteadmin, Publish. Now check to see if it worked at the REST Directory, and you will see Canada map! You can now create a web map using this layer (via add item URL on AGOL).

**march 3:**
* :alarm_clock: 8am: clicked through optional items of week 7/8 checklist - found Shawn's demos on Geoserver interesting and followed his 5 step series on youtube (https://www.youtube.com/playlist?list=PLa8md6Vlz64JqOvr5P0Hua3LTVsmTpajF). from shawn's videos I discovered QGIS, which I then went on a side quest to trial and play with. Downloaded some roads data from QGIS's tutotial section (https://www.qgis.org/en/site/about/index.html).
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/9f30d5ac-5976-491c-b4b1-6daf2dbee08d)
* :alarm_clock: 12pm: satified with checklist and learned a lot. An interesting thing I now know is that you can use GeoServer to your advantage and it can host your data, reducing your AGOL credits! Also, got to discover QGIS a bit :)

**march 10:**
* :alarm_clock: using chloe's and rajesh's client - city of cambridge (https://geohub.cambridge.ca/pages/operations) - dashboards to click around and play with the interface as i am not familiar. very cool interface but am concerned as to how we will show indoor floorplans / room info on this interface. leaning more towards experience builder...
* ![Screenshot 2024-03-08 085659](https://github.com/aherstek/markdown.md/assets/146446987/754949f3-6427-458d-b5fa-b9673cde5c47)

**march 12:**
* :alarm_clock: found UDOT open source data on AGOL. Business building located in Utah. Group okay to use this. Uploaded into ArcGIS Pro to have a better look and play around with the layers. Plan to upload to AGOL Group once Shawn shows us how to in lecture.
* ![Screenshot 2024-03-12 094121](https://github.com/aherstek/markdown.md/assets/146446987/209adc4b-c54d-4ce9-be65-00b8d51ce3a8)

**march 13:**
* :alarm_clock: started to play with our UDOT data in ArcGIS Dashboards. Finding it difficult to easily display the multilevels. Experimented for a little bit to familiarize myself with the interface. Opened/closed settings, switched up layout.
* ![Screenshot 2024-03-13 153250](https://github.com/aherstek/markdown.md/assets/146446987/53482104-fe32-4fc8-ab04-0c9b430f4ce6)

**march 14:**
* :alarm_clock: trying to deploy floor widget in experience builder so user can view each floor independently... not working yet (view, view 2, view 3). having so many layers of a building at once is proven to be difficult to display in a easy way! also count not get the 'directions' widget to link with the UDOT data - I believe I need to select a floor but could not find where to do so. *REMEMBER* you need to unlock layout lock to access your widgets!
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/959f5526-d143-4692-b22d-b1fb0eb27f84)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/5bf5c3bb-731e-4aff-b62f-d39cb7441b81)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/b06fbfe7-01f2-44ad-89dc-b3d16edc31d5)

**march 15:**
* :alarm_clock: met with shawn with GEOM99 group 4 - he introduced us to AGOL Solutions! This is what I will begin to look into this weekend. :)

**march 19:**
* :alarm_clock: _start time: 2:45pm_ working through many trials and errors of experience builder's widgets. i spent ~2 hours clicking through the many widgets to see which could best suit floorplan data.
* :alarm_clock: i took today to simply learn and play about widgets. i opened experience builder, made a brief little title/image sidebar and imported UDOT map. I then made a large area below/beside these sections to then one by one select a widget i was interested in and click through the settings, try to get it to work, etc - all to see how valuable it may be to my groups geom99 project. below i have listed the widgets that either i learned something new with, did not work, or i think could be useful for future use. i have rated them on a scale of 1 to 10 for quick reference.
  
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/6c31eb43-dba1-44d2-8b9f-74b2dfe5c906)
* :alarm_clock: ^ above is the 'map layers' widget that allows you flick floors on and off to see from above. it works, but not visually appealing. i rate 2/10.
  
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/ad201250-9e13-4657-b2ca-6fbdcfd896e5)
* :alarm_clock: ^ next i tried the 'near me' widget which i thought i could set up to direct one to various sections of the building but it is not compatible... so 0/10.
  
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/8244641c-6889-452a-97f3-33e55185476d)
* :alarm_clock: ^ similarly with 'network analysis' i was hopeful to be able to experiment with this but alas.... no... 0/10.
  
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/45598461-f8f4-49a8-b474-142cd4a9f94e)
* :alarm_clock: ^ then i tried 'floor filter' which isn't "floor aware" of our data... i want to look into this further! i am curious, so 3/10. look into this documentation: https://doc.arcgis.com/en/experience-builder/latest/configure-widgets/floor-filter-widget.htm and https://pro.arcgis.com/en/pro-app/latest/help/data/indoors/floor-aware-maps.htm
  
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/40049d78-9bd4-423c-a466-c2a2f4fccfa7)
* :alarm_clock: ^ above is the 'directions' widget which i thought i could maybe use for an indoor space but i learned it is only from one outdoor address/building to another. could be useful for a building such as a school for staff/students to know how long it will take to get there from their home, to a field trip, etc... 4/10 could be useful!
  
* :alarm_clock: overall, i am feeling a bit discouraged to how to display floorplans that are not "floor aware". i am now going to look into a way through ESRI products to make our floorplans easier to use these widgets! maybe dashboards may be a better solution? plan to touch base with group for feedback tonight.  _completion 4:42pm_

**march 20:**
* ⏰: _start time: 12:00pm_ still trial and erroring widgets in experience builder.
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/d5a44ee7-ae96-425d-b618-5ac2f93d03cc)
* ⏰: ^ i have map widgets which allow you to click on the map which pulls up attribute table. i am thinking we can clean up which fields are shown (only useful info). i thought that maybe using just the floor outlines (pictured on the left in image above) may work better to see floorplans in experience builder but it unfortunately operates the same as yesterday's workflows...
  
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/159bd0ca-7992-461b-ab1d-37e5a89317d1)
* ⏰: ^ i did accidentally discover by clicking the 4 dots and "show on map" it highlights the selected areas in the left map that were chosen on the right map... need to figure out how i linked this. could be useful for someone looking for a certain department / specific room use throughout the building?
  
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/4c0bab71-fdd9-4aa4-8709-016e8fd10d1d)
* ⏰: ^ another example of clicking on right map, selecting a section and it highlighting on right map after "show on map" is selected.
  
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/a841a305-de4c-47d2-b36f-f2874d05d7ff)
* ⏰: ^ while looking at the tools in the "map" widget, i saw the tool "select". using 2 different icons provided (arrow with square, magnifying glass with square) you can select elements of the map. when trialling, this tool selects multiple features at once (as seen in image above) which i couldn't figure out how these features are chosen as i clicked on a sigular line (or so i think?). i think this tool could be useful for someone to use for the not line-based floorplans (the layers with allocated, coloured rooms) so someone could select certain rooms to learn more about them? i will try this next.
  
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/e6060f4c-46c8-4c44-bf40-110824210348)
* ⏰: ^ tried the "select" tool for the coloured map floorplan - i think it worked but with the multi-layers it was hard to see what was happening.
  
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/9fef9d48-4709-471f-91d2-68da0cd53e6b)
* ⏰: ^ i turned off all layers but one, and learned the select tool does choose all rooms of the same colour! i can't seem to see the 'selected features' attributes, as clicking on this icon just zooms in on the selected areas....
  
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/ee0822bb-be41-473f-aeae-68603e8775a4)
* ⏰: i am now looking into the analysis tab.... so so so many resources here! as i was looking into possible analysis we could use, i noticed that these use credits to run (is that ok for us to do? i don't want to cost shawn $$$!!). for now, i am going to read into these analysis options just to see which might be good to play with for floorplans / indoor spaces to share with my group.
  
* ⏰: **SPATIAL ANALYSIS TOOLS**
* ⏰: i looked through _a lot_ of tools, but opted not to trial them all as they cost credits. these are the tools i chose to try, or found interesting enough to document.

* 🛠️ how to set up: drag the analysis widget into your dashboard. a window will pop up on the right to allow you to choose which map you wish to analyze, and which tool you wish to use. once selected, you will add your query / information / etc directly into the widget. the analysis runs directly from your widget. confirm your ESRI email is correct, and name your output. you can even check how many estimated credits your run will cost. once finished, the widget will show your outputs on your chosen map, as well as your item id and link to AGOL layer. if you click the back arrow in the widget, it brings you back to all of the tools you have used to keep track of your analyses.
  
* ⏰: 1) _"find by attributes and location" -trialled, 0.221 credits spent_
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/e301d9e7-2929-4573-9084-59c13ad74286)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/cb0ac20d-daeb-4f5c-8604-567a7ffa003e)
* ⏰: output here: https://fleming.maps.arcgis.com/home/item.html?id=0daab7d399b44f6d97995c278fd60e21
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/526658c5-fcf9-49ed-830d-9fcb51b91b4d)
* ⏰: ^ query worked and displayed elevators on floor one as requested! not sure how this could be completely utilized for user's in a quick way (as querying isn't super user friendly for a non-GIS user but for internal use it would be cool to query X,Y,Z to find locations etc :) i am happy this was successful!
  
* ⏰: 2) _"deep learning" - not used, just think is cool_
* ⏰: i saw that there are 5 "deep learning" tools that utilize AI/computer models to create your outputs! a little too complex for this, but i think we could have taught it to classify rooms/ their use etc!
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/2b35669b-1139-483e-bff8-058540b95e22)
* ⏰: further documentation i read here: https://doc.arcgis.com/en/arcgis-online/analyze/classify-objects-using-deep-learning-mv-ra.htm
  
* ⏰: 3) _"choose best facilities" - could not use, data not compatible_
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/98832ef1-5acc-4446-b9bc-31a0598621e8)
* ⏰: i think widgets like this one could be cool to use indoors to calculate walking time. when trying to get it to work, i learned that our floor plan data was not compatible. seems to be a trend 😢
* ⏰: documentation read here: https://doc.arcgis.com/en/arcgis-online/analyze/choose-best-facilities-mv.htm

* ⏰: 4) _"dissolve boundaries" - trialled, 0.221 credits spent_
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/62bd093d-0e45-4dce-a046-b92d74ab4dff)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/d60faea5-d8b9-407a-8361-7ba012266183)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/da0b376e-9019-405a-9dab-54ff118061e1)
* ⏰: ^ this tool worked as well!! yay! i used the same floor as experiment #1, choosing the groups attribute to dissolve by... also calculating total area. not sure how valuable this tool is? or if i did it correctly, but from this i learned that these analysis tools can be utilized to learn more about the areas/size/groups/names of this building.
* ⏰: output here: https://fleming.maps.arcgis.com/home/item.html?id=6766f8b6cab04f58885566b8b58a7fe2

* ⏰: documentation to analysis tools i looked into, but did not trial yet (leaving links here for future me to reference)
* ⏰: aggregate points: https://doc.arcgis.com/en/arcgis-online/analyze/aggregate-points-mv.htm
* ⏰: join Features: https://doc.arcgis.com/en/arcgis-online/analyze/join-features-mv.htm
* ⏰: find similar locations: https://doc.arcgis.com/en/arcgis-online/analyze/find-similar-locations-mv.htm
* ⏰: enrich layer: https://doc.arcgis.com/en/arcgis-online/analyze/enrich-layer-mv.htm
* ⏰: distance allocation: https://doc.arcgis.com/en/arcgis-online/analyze/distance-allocation-mv-ra.htm
* ⏰: overlay layers: https://doc.arcgis.com/en/arcgis-online/analyze/overlay-layers-mv.htm (to combine the skeletal/line layer of each floor to the coloured/polygon layer of same floor?)
  
* ⏰: in all - today was super cool working through the analysis tools. i learned that many are not able to run due to how simplistic our data is, but other analysis tools we can utilize (for credits per query / run / etc). i want to allocate a bit more time this week (if possible) to learning experience builder tools so i have a full comprehension of them to present to shawn on friday, and to my group prior to this!
NOTE: remember to "lock layout" before viewing your widgets so you can view it from a user standpoint so you see what they would see when using it! _end time: 1:45pm_

**march 28:**
* ⏰: _start time: 12:30pm_
* ⏰: today i have 2 goals... 1) to play with scene builder and 2) is to create a fully curated, nice looking experience builder dashboard. i have played with the tools and am now familiar with the interface, but want to bring these elements together into a visually appealling user interface. my goal is to make a dashboard that allows the user to better understand room level/navigational information of UDOT building - as well as a (hypothetical) nearby park.
  
* ⏰: _scene builder_
* ⏰: i imported a layer i created during my experience builder trials so i can better understand what scene viewer has to offer! right off the bat, i noticed that you can adjust the time of day and weather on your layers, to accurately display shadowing and sun positioning (so cool!). this can be found by clicking the sun icon on the right, titled "Daylight/Weather".
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/5d76ac7e-f9b8-4856-b899-dcc7873ea8ce)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/e790a2d4-6356-4444-8c5f-25e8688c28a0)
* ⏰: by clicking "present" and using the control toggles on the left, you can see your imported layer as 3D. i played around with displaying layers on their own, stacked, and with the "mock" building overlaid on top. personally, i think the layers by themselves stacked (and colour coded) looks cool but i'm unsure of the functionality / when this would be useful to have. i am now going to try to import this ino my experience builder if possible (and once i make it look a bit better/see other analysis options!)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/8f2a0f89-d2d5-4ec3-a166-29cfd8ffb490)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/004bf677-6752-4b8a-bb2e-f8c35211cb51)
* ⏰: slice layer allows you to drag the exterior walls up and down using the large orange arrow to see internal floor plans!
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/a82c534a-314f-4a08-923a-118fa3814373)

_experience builder_
* ⏰: starting from the EB template I started last week, importing 2 Map widgets, 2 text widgets and 2 image widgets and playing around with the layout. I realized that the initial 3D scene map I created wasn't very functional - so opted to remove for now. 
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/919cce6e-3ec1-40be-b231-486b84b1eb45)
* ⏰: I GOT A ROUTE TO WORK !!!
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/fbc9bbbc-bd24-4241-8189-7858c747a5dd)
* ⏰: Using the "Directions" widget, you can click your starting and ending points on the below map and it will generate a route!
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/175b5536-1d45-4cc7-b21d-43162e9f2da4)
* ⏰: Another example of output, showing time and directions step by step
  
* ⏰: a (simple) but functional dashboard! :exclamation: :exclamation: it doesn't make too much logical sense - but my goal was just to have multiple features in a dashboard up and running - which i accomplished. routing for outdoor areas was a simple workflow - but the indoors portion is still challenging. 
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/3fc799b5-8da3-4147-9adb-c0573083b4f5)
* ⏰: this dashboard allows a user to do the following functions:
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/2e00b08e-ee22-495c-aaef-579274004b06)
* :exclamation::  ^ select all attributes within a selected area (which then can be exported or queried)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/1aad5499-c343-4604-bf30-f940807e74eb)
* :exclamation:: ^ using 'selected features' tp query rooms and floors
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/14d76043-fd81-4c5f-acf7-b25badace400)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/543333c4-0947-4603-8612-7409bd1bce1e)
* :exclamation:: ^ create routes with stops depending on user's selected mode of transportation 
* ⏰: *next steps*
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/85ec32ef-2fc4-40dd-b150-cd78bf4c7b18)
* :exclamation:: ^ input the 3D imagery I created in Scene Viewer somehow and making it look better than my initial trials (in screenshots from today)
* ⏰: overall, creating this dashboard took me much longer than expected. i forgot how much time it takes to create a nice looking layout... plugging in the widgets and setting them up was the easy part! lol :exclamation:: this weekend i will continue to work on our webpage: https://georajesh.github.io/geom99-project/index.html where we will display the many ways we have experimented displaying room data and navigation within ESRI products.
* ⏰: _end time: 3:25pm_

**april 3:**
* ⏰: _start time: 9:00pm_
* ⏰: continuing with experience builder...
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/8e40f463-d11d-4377-a015-606d8cb1e945)
* ⏰: ^ using the "swipe" function to allow users to look at different features of floor plans. "leading" layers i selected to be the skeleton floor plans, and the "trailling" layers i chose to be coloured, blocked out floor plans of the rooms. i chose to allow all layers to be swiped on, but you could choose a certain floor for a better, detailed idea of the layout.
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/57c1117b-0720-4477-a0b1-ad4ad3cdf6c5)
* ⏰: ^ within the swipe widget that you put on your dashboard, you can also allow users to decide which floors they want to swipe between (from my pre-determined "leading" and "trailling" selection you choose in the settings)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/4f91b124-b19e-4a78-bd0d-7efbbb11c4f6)
* ⏰: **NOTE** there are some important icons on top of every widget you place in experience builder. i spent way too long trying to find a lost widget when i (in hindsight) probably accidentally clickedv"send to back" allowing all other widgets on top of this one. the 3 stacked squares icon accounts for this, and allows you to choose how you wish to stack and layer your widgets if necessary. the icon beside it, a lock, can lock and unlock your widget's location and size - essentially freezing it place. i found this widgets very helpful once i figured them out!
* ⏰: within the swipe tool, there are basic and advanced "swipes". the one i display above is the basic version, but i now am going to try the advanced setting. this advanced layout allows the user to swipe between multiple floors of your choosing in a more seamless fashion.
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/3f61a7a7-1030-47f8-abd6-6549835ced1c)
* ⏰: ^ in this swipe, you can use the horizontal scroll bar to move left and right to view the floor plans individually. i chose to display floor plan B, 1, 2, 3, and 4 (blocked, coloured layers) so the user could slide across and see each layer of the building, basement to top! like mentioned in the badic version, the user has control to flick on and off the layers of their choosing using the swipe widget locked to the map.
* ⏰: another feature i found was in the "card" widget, which allows for photos, a title and subtitle, etc - you can lock this to the top, bottom, L or R side of your dashboard. something cool i discovered and played with was having multiple slides, kind of like a presentation that you can automate to flip through.
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/a38f5430-8090-4b24-94f2-62f6cf6eab00)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/c6e808c7-2f6a-4be1-a293-aa3a110c59d7)
* ⏰: ^ the "2/2" at the top of the first screenshot lets you know which view you are editing, which you can switch up the layout from the previous view. the second screenshot is the settings, which you need to flick on "automate" and you can set your intervals for it to cycle through your views within the widget. i think this is neat because if you have lots of information to share / info how to utilize the dashboard, you can do so without taking up too much space on the dashboard itself.
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/ab5e83f5-08a3-412d-94c3-2e5e32d4752b)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/21c729a4-b0e0-4ada-8473-3663833e03e5)
* ⏰: ^ couldn't get the formatting quite right yet on the second view, but this is what the user sees (i chose a 5 second interval) on the dashboard.
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/894987f4-9c13-4057-aea9-3fea06ad392e)
* ⏰: when going to publish, i was met with this screen ^ and i opted to not publish because i was scared i was going to use up credits etc. still saved dashboard to my AGOL account and in my geom99 group, just opted to not re-publish just in case!

  
* ⏰: overall, i didn't make too much progress today as small roadbumps took up a lot of my time. i had hoped to polish my dashbard up (which i kind of did) but i did not get to putting my scene viewer map into the dashboard. i will work on this tomorrow so i can have my finalized experience builder "solution" ready to show shawn on friday during our technical meeting :)
* ⏰: _end time: 11:00pm_

**april 4:**
* ⏰: _start time: 6:30am_
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/eff44985-1bd0-43b1-946f-1d5068a606cc)
* ⏰: this is what i have created so far in my practice and experimenting. the dashboard has an info widget that flips through informational views, a routing of outdoor park, and a floormap map that can be queried and the layers swiped through to see floor by floor.
* ⏰: what i want to do it utilize scene viewer and try to get it into a dashboard and see what we can do differently in regards to navigation / querying / displaying information about the building. tali created a nicer looking scene viewer output than i did, so i will be using hers to save me time to actually work on the dashboard's outputs.
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/2f8400f2-8758-4a18-8109-45af4c47d32c)
* ⏰: ^ i have chosen a different experience builder layout, and will spend the next little bit editing the text and "cartographic" parts before moving onto trial and erroring the scene viewer portion.
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/b160967d-6ac8-4c83-84fa-d47f5d329f11)
* ⏰: ^ trialling using the "search" function within the map widget for the user to be able to search something such as "elevator" on the floors.
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/0cd30321-5fcc-4f72-a453-c19750079052)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/78084a5f-6170-4522-8425-cee6eed0cf3d)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/c187f84b-c614-4bb7-87bf-2dff269cfc65)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/5af93d30-8a40-4eb9-921c-4ea5cc35400a)
* ⏰: it works!! after setting up my settings as such ^ allowing for the user to search floor, name and group (with exact match turned off so they could still potentially get results without exact spelling) i was able to type in "elevator" and it displays all elevators per floor - and then when you click on a specific one it highlights it on the map for you!!! 
* ⏰: this is what i had been working to accommplish since starting this project so i am thrilled i got it to work. i was discouraged as the initial floor plans were not "floor aware" so i felt as though i could not accomplish what i wanted - but scene viewer saved the day! i am now going to continue to work on my dashboard and see what else i can get to work!
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/5bb162cd-7cf4-45e0-b237-918fb46d7984)
* ⏰: ^ i enabled a pop up for when someone firsts clicks onto the dashboard, this would be great for informing someone how the dashboard works, or any important info.
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/7dd03175-cb3d-433d-9e40-b161c67daa10)
* ⏰: ^ you can do this my going to "window" instead of page and selecting "fixed" windows
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/8cd0ebdf-182a-4101-88e8-651cbd5eca54)
* ⏰: ^ other than my poor colour scheme that makes the selected area hard to read - the function works well. i chose "admin" and it pulled areas/rooms that have admin in their name. i clicked on one, and it (faintly) highlights the area. i tried to see how to darken the highlight colour but can't seem to find where / if possible. once something is selected, it shows the user the # of selected features in the bottom right, which if you click on it - it zooms right to the area from a birds eye view. this gets a bit jumbled with the many layers stacked on top, but you can turn them off in the layers/legend buttons at the very top right for easier viewing.
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/b86547e2-cdbe-4722-baf3-c4a6f2604d51)
* ⏰: ^ legend and map layers buttons at top of dashboard
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/5f95dbfe-7579-44ce-9fbc-6e42b9e340f8)
* ⏰: i wanted to try and add the swipe feature like i have in my other dashboard, because i thought it would be cool to utilize in a 3D space - but unfortunately it is not supported.
* ⏰: **NOTE** i have noticed that the dashboard utilizing scene viewer data runs a lot slower than my 2D dashboard, and if you move around quick the image quality becomes fuzzy and pixelated. just good to note if thinking of using a large dataset of floor plans in the future!
  
* ⏰: overall i am very pleased that in the end, i accomplished my goal of being able to obtain room level information and it's location through a simple search bar using UDOT's data. unfortunately i could not get the navigational part to work for indoor data (UDOT data was not 'floor aware') but i did get routing to work for our outdoor park which was exciting. **lots** of trial and error and playing around, but i feel as though it was very valuable because i gained 2 new skills: experience builder and scene viewer, both of which i had no working knowldge of before - and now i am very confident i could recreate this again and improve my skills even further.
* ⏰: _end time: 8:30am_
  

**april 6:**
* ⏰: _start time: 7:30pm_
* ⏰: tonight i will work on polishing up my 2 dashboards (try to figure out how to better highlight selected items in 3D dashboard maybe?) but i am done experimenting at this point. once i am satified with the 2 final products - i will continue to work on Group 4 websites.
* ⏰: so, today will be tips / tricks i find about the "aesthetic" side of experience builder, as i have mainly been focusing on the technical portions via widgets and not caring too much about the settings of _how_ they look, just how they work :)
  
* _3D dashboard_
  
* ⏰: first i will try to read some documentation if it's possible to change the highlight colour during the select tool
* <img width="621" alt="image" src="https://github.com/aherstek/markdown.md/assets/146446987/f16045ee-50da-4ba3-a24f-210f225be686">
* ⏰: ^ update: after ~20 mins clicking through every setting and referring to some stack exchange discussion and it seems as though you cannot. the only thing i can think of is going back into arc scene viewer and altering the colour scheme to better display the experience builder highlight colour, but i do not have time to do that - nor is it that important. but, an important thing to note if really highlighting the selected room is important to the user.
* <img width="119" alt="image" src="https://github.com/aherstek/markdown.md/assets/146446987/28becde9-625b-482c-9a63-f45c358bbe19">
* ⏰: ^ my first concern in regards to visual appeal is that when selecting a "theme" colour - i chose a dusty, salmon-y pink?, it skews all your widget icons to match the theme colour which makes the icons hard to see. in my case not a huge deal, but for someone who is visually impaired, or new to using a dashboard it would be hard to navigate. i found that darker theme colours selected provided more contrast for the widget buttons.
* <img width="286" alt="image" src="https://github.com/aherstek/markdown.md/assets/146446987/80b16b63-f0b9-4a15-b3f5-67d6dcb7ab93">
* ⏰: ^ you can change the colours of the widgets by clicking on it's icon while the layout is unlocked, choosing "advanced" settings which will allow background colour and font/size options
* <img width="666" alt="image" src="https://github.com/aherstek/markdown.md/assets/146446987/e6c9e0d7-4eea-4857-b688-92b896d262a3">
* ⏰: ^ i also experimented with how different screen sizes look with their auto formatting function (example above is how my dashboard would be seen on a tablet). experience builder essentially tries to fit your widgets into the screens dimensions by condensing / creating a layout automatically. i trialled with different dimensions which you can alter beside the 3 "screen" sizes (square shapes). overall it did an okay job to try and accommodate your data into the new screen size, but i did find in smaller mobile screen sizes that some widgets got lost.
* <img width="1440" alt="Screen Shot 2024-04-06 at 9 58 32 PM" src="https://github.com/aherstek/markdown.md/assets/146446987/d825c803-bcdc-45b6-b9c6-4f443925ebea">
* ⏰: ^ its also good to note "page" vs "window" screens - it is the second icon down on the left side. "page" refers to your main dashboard and it's associated widgets and "window" refers to pop ups and infographics you automate to display info etc. far too often i was on the wrong screen and couldn't figure out why the settings i wanted were not showing up. so if you're stuck - make sure you're on the right screen you're lookinh for!
* ⏰: within the "window" settings on the right (in above picture) you can modify if the window pop up is fixed or anchored, what the user must press/enter to close the pop up and the colours/font/size. i found this to be neat, especially when you want to ensure that someone has read pertinent information provided on how to use the dashboard etc - and has to click a button / type a phrase before proceeding!

_2D dashboard_
* <img width="734" alt="Screen Shot 2024-04-06 at 10 15 23 PM" src="https://github.com/aherstek/markdown.md/assets/146446987/11eda0e2-7898-4811-800b-51feb1a327b7">
* ⏰: ^ something i found helpful (though they are tricky to place, especially rotate) are these dashed markers to divide your sections. no purpose other than organization, but helpful to guide your user around the dashboard and give some blank space for balance.
* <img width="244" alt="image" src="https://github.com/aherstek/markdown.md/assets/146446987/2f968508-536b-4bdd-9a09-11662174281b">
* ⏰: ^ in the 3D dashboard, the arc scene viewer floor plan map took up 90% of the dashboard's surface - not allowing for many other features. in this 2D dashboard, i had a lot of space to place smaller widgets. at the buttom of the widget selection are these 3 areas - all of which help _organize_ the widgets you place... a widget to help another widget... widget inception? lol. the "menu and toolbars" allow you to condense widgets into icons if you have lots you want to display - and the user can decide which is brought to the forefront. "layout" is quite self explanatory - controlling the flow and size of the widgets and organizing them. a cool one is grid (which i used) which creates patterns of squares that you can then plunk your chosen widgets into - so the sizes are consistent and look good together. thirdly is "sections" which allows for better user navigation - one of which being "views navigation" which gives users the power to flip through the sidebar view at their own pace, if the automation the owner chooses is too slow/fast for their liking!
* ⏰: at the top of the widget bar there are 2 subtitled, "new" and "pending" - "new" is dragging a new widget into frame and "pending" is one you have started/are working on. i thought i lost a widget at one point until i realized it was in the "pending" list so if you think one is gone... look there!
* <img width="412" alt="image" src="https://github.com/aherstek/markdown.md/assets/146446987/3e5502a7-d02c-43de-b7e0-4a447bf7251d">
* ⏰: within each widget placed - if you click on it, it will bring up an array of additional icons that allow for further editing. they are (L to R): align (snap to left, right, top or bottom), arrange (bring forward, push back, stack layers), lock position and size, duplicate, move to pending list (if wanting to further edit), delete, shape (not available for all widgets - only photo and text), and crop (not available for all widgets ex. can't crop an analysis widget).

* ⏰: clicking through the **many** widget options, colour/font/text/layout/shape/etc styles took me way longer than anticipated. but, i feel as though i now have a good grasp on how to better layout a dashboard and really utilize all it has to offer!
* ⏰: next (and final?) steps are the github website - i hope to make either detailed screenshots or gifs (if i can figure that out) of my dashboards to display them as a solution.
* ⏰: _end time: 11:00pm_


**april 7**
* ⏰:_start time: 10:00am_
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/f33499f6-72d0-4105-a02a-d498e38eaf49)
* ⏰: ^ trying to create a gif to upload into github website - i screen recorded a small clip of using the dashboard, imported into clipchamp to the export into a gif.

