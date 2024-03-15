# andie's technical activity log 2024
# my personal time log for geom99 group 4: https://docs.google.com/spreadsheets/d/1UeDhiMlVg55BBoP2paiI3WA6aODq5btSCYPUxrXSli0/edit?usp=sharing

_**february 29th:** setting up markdown.md doc in githubt and learning md syntax from here: https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax_.

**march 1:**
**week7/8 checklist notes and timeline**
* :alarm_clock: 8am: Started my own ArcGIS Server on Google Cloud Platform. Followed Shawn's instructions (https://youtu.be/dyFeyBX9jIY) to get everything up and running. NOTE: document all passwords / IP addresses / important information Shawn addresses in the video in Notepad, as some information is only shown to you once and it is helpful to have it all safely stored.
* :alarm_clock: 9am: VM up and running. REMEMBER to turn off VM when not using! You can ensure that everything is turned off my seeing a "stop" icon on GCP and shutting down VM from start menu.
* :alarm_clock: 1115am: Contiued to work through checklist steps - publishing on GCP VM into ArcGIS Server (Canada.shp used from prior weeks).
* :alarm_clock: 345pm: Completed checklist. Overall it was a bit challenging - ESRI documentation and Shawn's notes/videos were helpful when stuck.

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
 * :thumbsup: we are now ready to proceed into arcgis ! :smile:
 * ![image](https://github.com/aherstek/markdown.md/assets/146446987/91400e87-ee01-40b0-84f5-6b0caee32e75)
 * :thumbsup: when shutting down server --> 3 dots, **stop** and wait until status icon is grey.

**march 3:**
* :alarm_clock: 8am: clicked through optional items of week 7/8 checklist - found Shawn's demos on Geoserver interesting and followed his 5 step series on youtube (https://www.youtube.com/playlist?list=PLa8md6Vlz64JqOvr5P0Hua3LTVsmTpajF).
* :alarm_clock: 12pm: satified with checklist and learned a lot. An interesting thing I now know is that you can use GeoServer to your advantage and it can host your data, reducing your AGOL credits!

**march 10:**
* :alarm_clock: using chloe's and rajesh's client - city of cambridge (https://geohub.cambridge.ca/pages/operations) - dashboards to click around and play with the interface as i am not familiar. very cool interface but am concerned as to how we will show indoor floorplans / room info on this interface. leaning more towards experience builder...
* ![Screenshot 2024-03-08 085659](https://github.com/aherstek/markdown.md/assets/146446987/754949f3-6427-458d-b5fa-b9673cde5c47)

**march 12:**
* :alarm_clock: found UDOT open source data on AGOL. Business building located in Utah. Group okay to use this. Uploaded into ArcGIS Pro to have a better look and play around with the layers. Plan to upload to AGOL Group once Shawn shows us how to in lecture.
* ![Screenshot 2024-03-12 094121](https://github.com/aherstek/markdown.md/assets/146446987/209adc4b-c54d-4ce9-be65-00b8d51ce3a8)

**march 13:**
* :alarm_clock: started to play with our UDOT data in ArcGIS Dashboards. Finding it difficult to easily display the multilevels.
* ![Screenshot 2024-03-13 153250](https://github.com/aherstek/markdown.md/assets/146446987/53482104-fe32-4fc8-ab04-0c9b430f4ce6)

**march 14:**
* :alarm_clock: trying to deploy floor widget in experience builder so user can view each floor independently... not working yet (view, view 2, view 3). having so many layers of a building at once is proven to be difficult to display in a easy way! also count not get the 'directions' widget to link with the UDOT data - I believe I need to select a floor but could not find where to do so. 
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/959f5526-d143-4692-b22d-b1fb0eb27f84)
* ![image](https://github.com/aherstek/markdown.md/assets/146446987/5bf5c3bb-731e-4aff-b62f-d39cb7441b81)

**march 15:**
* :alarm_clock: met with shawn with GEOM99 group 4 - he introduced us to AGOL Solutions! This is what I will begin to look into this weekend.

