# Week 06 Projection 

Use the knowledge gained last week in lecture concerning the mathematical, historical and political issues on map projections to now be responsible for creating one for your project basemap. 
 
 [Week 6 Worksheet: Projection](https://github.com/cwilmott/GEOGC183/blob/main/assets/C183%20Week%206%20-%20Projection%20.docx) Click the download icon in the top right, I promise the file is there.
 
 [Week 6 Lab Discussion Slides: Projection](https://github.com/cwilmott/GEOGC183/blob/main/assets/C183%20Week%206%20-%20Projection%20Lab%20Discussion.pdf) Slides Jack discussed in the evening, take a glance if you want to understand the context of the foundations walkthrough. 
 
 [Week 6 Lab Walkthrough: Projection](https://scribehow.com/viewer/Lab_6__Projection__MR2X2m2KRSan4Jm8zmJ8ow) Direct link to the scribe website if this is more accessible for students!

 [Week 6 Lab Data]() *Clancy add link to bCourses File section before AM Lab* 

 *Optional Resources*

 [Leventhal Map Center Projection Exhibit "Bending Lines"](https://www.leventhalmap.org/digital-exhibitions/bending-lines/how-to-bend/projections/)

 [Bill Rankin Projection Guide and Experiments](http://www.radicalcartography.net/index.html?projectionref)

# Foundations Walkthrough

Using the freelance project request from a book publisher, we will go through the first step of determining the contextually appropriate GCS/PCS/Projection system for the Great Basin regional scale. 

1\. **\[0 - NOT PART OF THE WALKTHROUGH\]** Refer to this step of the tutorial should you encounter this problem in future cartographic work.

Something I won't have you practice is the scenario when a GIS data layer possessing an **Unknown Coordinate Reference System** is added to the [[Map ]]processing frame.

Use this [**quick and dirty tutorial from an instructor at U-Mass Amherst**](https://youtu.be/kOv1tgGw9Ss?si=gtziosA8bT9qqSZC). He identifies the common issue, and which tools you use in [[ArcPro ]]to quickly resolve the crisis.

The steps you follow below are part of the troubleshooting process you'll undertake when this (inevitably) happens.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-28/51dbdd86-3c3d-47e3-9e35-e8c8e3b8c137/screenshot.webp?tl_px=0,0&br_px=912,473&force_format=jpeg&q=100&width=913)


2\. Navigate to your desktop file directory

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/77d3b058-66a3-44fa-a5ed-1fd1dcb356a7/ascreenshot.jpeg?tl_px=0,310&br_px=1376,1080&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=210,576)


3\. Within the file directory, navigate to the [[!geographer]] folder. This will store data you create onto this specific desktop.

It is advised to bring a flash drive or figure out your own cloud-based method for storing the data if you wish to work with your data elsewhere.

Otherwise it will be on this computer, in the CAGE Lab.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/1892248a-e9e5-4bc9-87ea-b43487556502/ascreenshot.jpeg?tl_px=0,244&br_px=1376,1013&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=493,277)


4\. Create a new folder on your directory of choice, and title it **Lab6Projection_LastName**

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/45956dfb-7d31-4b72-8a3a-6e3fee1da346/ascreenshot.jpeg?tl_px=307,84&br_px=1683,853&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=524,277)


5\. Right click within the folder or use the keystroke [[Ctrl+Shift+N ]](Windows Users) to create a new folder within the Lab6 folder.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/217e574d-f340-4cb7-bd9c-a319cfb9ac80/ascreenshot.jpeg?tl_px=326,245&br_px=1703,1014&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=524,276)


6\. For every GIS/Cartography project you work on, it is always best practice to name the project folder as it relates to the project you are working on.

In this case, my project is for the Great Basin region. So I will name it [[GreatBasin]]

NOTE: When you eventually interface with advanced computing and navigating files via a coding terminal, it makes life a bit easier if you combine names together or utilize underscores. Code is case and character sensitive.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/53815e3c-7a83-41fa-ba28-8e2f4af8d7aa/ascreenshot.jpeg?tl_px=0,6&br_px=1919,1080&force_format=jpeg&q=100&width=1120.0)


7\. Create a new folder within the project folder, and name it [[Data]].

As you will begin to see in future lab assignments, your project directory will consist of subfolders such as "pdfs", "case studies", "research", "meeting notes," etc.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/494646f4-a163-4f86-958c-402e222c92ed/ascreenshot.jpeg?tl_px=0,6&br_px=1919,1080&force_format=jpeg&q=100&width=1120.0)


8\. And yet again, create another folder within the newly created [[Data ]]folder. This one can be named along the lines of [[\_datacopy]]

It is always best practice to store raw copies of your data in its own folder. As you will come to learn, data gets overwritten once it is manipulated in a processing frame.

Always store a clean, raw copy of the data you collected so you can restart if needed.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/914ab517-6e26-4841-8eb0-fcc1fcf28530/ascreenshot.jpeg?tl_px=178,186&br_px=1555,955&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=524,277)


9\. Navigate to [naturalearthdata.com](https://naturalearthdata.com) and download their dataset **Admin 1 - States, Provinces**

This will download a [[.zip]] file with U.S. State boundaries at a 110m scale (small scale), and at a source spatial coordinate reference system of **WGS1984** (more on that once we are in ArcPro)

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/37ed3336-e698-4671-a5b8-b37efd400832/ascreenshot.jpeg?tl_px=106,0&br_px=1483,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=524,260)


10\. Navigate to <https://nbmg.unr.edu/geothermal/Data.html>

The Nevada Bureau of Mines and Geology (NBMG) is a research and public service unit of the University of Nevada and is the state geological survey. And thanks to their work, I can easily go and download an *authoritative GIS data layer* of the Great Basin hydrological boundary.

A good student will suddenly remember all the data classification and institutional power issues Clancy lectured on during the first few weeks.

Yes. There might be some issues in the grand scheme of cartographic discourse. And it is also true, that this data is the *most appropriate* GIS boundary files for my project context.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/5d84a90b-fbc9-422d-84d3-00bd17ba906e/ascreenshot.jpeg?tl_px=264,310&br_px=1640,1080&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=524,314)


11\. After downloading those two datasets as [[.zip]] files. Navigate back to your file directory and go to [[Downloads]].

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/9fdb3e14-d7ae-4b3b-8481-4dd7ea0e5022/ascreenshot.jpeg?tl_px=0,0&br_px=1376,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=165,20)


12\. Right click on the [[GreatBasinOutline.zip]], and select [[Extract All]]

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/8fcfe59b-9d0c-40a5-ae4d-fe5c42a0783c/ascreenshot.jpeg?tl_px=0,210&br_px=1376,979&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=429,277)


13\. Extracting a compressed ([[.zip]]) folder transports the large collection data onto your desktop.

Hit the [[Browse... ]]button and navigate to the project file directory you created at the beginning of the lab.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/682f391a-0592-48aa-9ea4-02d060af7246/ascreenshot.jpeg?tl_px=494,61&br_px=1870,830&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=524,277)


14\. Click [[Select Folder]]

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/f0bbd954-cfc3-4eca-ab9a-c59a0f5b1528/ascreenshot.jpeg?tl_px=544,310&br_px=1920,1080&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=681,380)


15\. Click [[Extract]]

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/46d8a682-4df4-4c46-9400-95f7832c7c3c/ascreenshot.jpeg?tl_px=452,310&br_px=1829,1080&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=524,292)


16\. And now the GreatBasinOutline data suite is in the project folder.

It is important to keep all the separate files *together* in the *same folder*. When the [[.SHP]] file is read into the GIS processing frame, it is reading all its accessory files structuring the [[.SHP]] file (i.e the .PRJ file stores the source GCS/PCS information).

A nice technical elaboration and diagram can be found here: <https://gisrsstudy.com/create-shapefile/>

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/274fc850-6ee7-430d-8676-6f5418ce64c1/ascreenshot.jpeg?tl_px=0,0&br_px=1376,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=292,31)


17\. Perform the same steps for the Natural Earth U.S. States data.

And now your [[Lab6Projection_LastName/GreatBasin/Data]] project directory has both datasets (it is advised to familiarize yourself with the basics of file path terminology and functions).

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/8e936f7c-31b3-4d6a-b501-d42cb0d286e2/ascreenshot.jpeg?tl_px=0,0&br_px=1376,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=305,35)


18\. Remember the [[\_datacopy]] folder you created in the beginning?

Move the two [[.ZIP]] file folders into[[ \_datacopy]]

*Is this necessary?* Not really. But when your projects become more complex, you will be thankful that you understand how to create 'fail safe' copies of your data. It will save you time not going back to the data portal and re-downloading it.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/cf65cfe3-e91e-41f6-a014-f8ef27a6d598/ascreenshot.jpeg?tl_px=0,0&br_px=1376,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=157,21)


19\. Additionally, you can create a copy of all the individual raw data files into the [[\\\\\_datacopy]] folder.

*Always always always* practice data management. It is not talked about enough in job descriptions. And that's the case since a hiring manager will assume you know what you're doing.

Get used to this now, while your 'client demands' consist of a P/NP lab assignment in a fun upper division class.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/54acc645-8774-496f-a0ea-cf0ddd79f38a/ascreenshot.jpeg?tl_px=0,310&br_px=1376,1080&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=487,384)


20\. In the desktop search engine, navigate to [[ArcGIS Pro]]

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/c759784e-2c6f-4f51-8e2e-d6d67e51d1ee/ascreenshot.jpeg?tl_px=0,0&br_px=1376,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=84,269)


21\. Click [[Map]]

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/bd2270db-15ab-4820-b006-9cc3ac52057a/ascreenshot.jpeg?tl_px=0,0&br_px=1376,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=193,174)


22\. Rename the ArcPro project to [[Lab6Projection_LastName]]

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/f712402d-90a7-492b-bfcb-2b8cf3995ff6/ascreenshot.jpeg?tl_px=211,65&br_px=1588,834&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=524,277)


23\. Finally!

Welcome to the [[ArcPro ]]interface. This is that desktop GUI Clancy and I always have a few choice words for.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/18e0d15e-54da-4700-9da9-6cdc97c14ec2/ascreenshot.jpeg?tl_px=0,0&br_px=1376,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=10,222)


24\. Recall a core concept from the History and Theory lectures. As a new GIS user, you are presented with a world so obvious that it is *normalized and unquestioned*. A world which emerges from a certain scientific research corporation, and their sets of practices.

Now is your chance to shake things up a bit. 

Select both of the default basemap layers and remove them.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/006f4940-a31f-4b88-a2ce-f654a2112a03/ascreenshot.jpeg?tl_px=0,13&br_px=1376,782&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=55,277)


25\. And now the world doesn't exist. Territory isn't real.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/50b72357-c95e-46a7-815a-e7b8d78786c9/ascreenshot.jpeg?tl_px=0,0&br_px=1376,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=36,3)


26\. From the [[Basemap ]]dropdown, select the [[Imagery ]]basemap.

If this is getting you excited, I advise diving into the world of basemap tiles.

One of my tasks at SFDPW was helping [geo-rectify a new USGS satellite image](https://gis.sf.gov/ipa/?lat=37.76&lon=-122.45) for the scale of San Francisco (to my knowledge not public facing yet). Play around with [[Inspect Element]] enough, and you can siphon the **tile server path**. And then you got yourself a nice basemap.

Soon, your basemap can be anything and can come from anywhere. Not only what the desktop GIS has to offer. **QGIS**, comes as a blank slate, with several basemap plug-ins that can be installed.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/01b56e5b-af9a-4896-95e3-c56b86186788/ascreenshot.jpeg?tl_px=0,0&br_px=1376,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=354,170)


27\. Under [[Add Data]], select the[[ Browse...]] option.

This will open a dialog box with the windows file directory, navigate to the [[!geographer]] folder.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/f7820a03-adce-4052-b1f4-40e15de3e4cd/ascreenshot.jpeg?tl_px=0,0&br_px=1376,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=384,98)


28\. Thankfully, I'm a good student who followed Jack's data management tutorial and can easily access the project file directory with my [[Data ]]folder

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/b13a639b-9861-4f37-9983-8959299cb542/ascreenshot.jpeg?tl_px=89,102&br_px=1465,871&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=524,276)


29\. Select both the [[GreatBasinOutline.shp]] and the [[ne_110m_admin_1_states_provinces.shp]] and add to the map

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/e8bc7e0b-7f69-4218-9d31-98198cac189f/ascreenshot.jpeg?tl_px=63,0&br_px=1440,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=524,202)


30\. Cool, this a perfect map and we can stop studying cartography forever.

All this research is pointless.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/0ba32c4c-72bd-4498-8514-a49cf1b49bbb/ascreenshot.jpeg?tl_px=0,14&br_px=1376,783&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=38,277)


31\. Either by double-clicking or right-clicking on the layer, **rename** both of your data layers.

NOTE: When in doubt, double click or right click. The dialog box you are looking for will appear.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/f3bdee86-1398-4009-b986-b36cc8eac7ae/ascreenshot.jpeg?tl_px=148,0&br_px=1524,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=524,270)


32\. Your new data layers should be named similar to this. Or any naming scheme of your choice.

A scheme for your layers is a huge component of data management. You will thank yourself in more complicated cartography projects when you take the extra couple of seconds to rename each layer.

NOTE: renaming the data layer in a GIS interface does not change the name of the file. Never change the name of the file. Yes, its ugly. But recall how the ESRI processing environment is directly talking to your project file path. If anything becomes renamed in the [[Lab6Projection_LastName/GreatBasin/Data/(data type).shp]] folder, your data will disappear.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/08911063-fe90-4a96-9a45-ba279b6e2a62/ascreenshot.jpeg?tl_px=0,150&br_px=1376,919&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=99,277)


33\. You are welcome to play around with the styles if the default visual design style hurts your eyes. Design is not the focus of this lab, so we will skip everything I do to change it up.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/a41b6c18-77e1-45b0-8efa-f3bc10d9d243/ascreenshot.jpeg?tl_px=544,0&br_px=1920,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=776,160)


34\. Right click on the [[Map ]]feature.

In ArcPro, [[Map]] acts as your [[Data Frame]] (for those of you familiar with coding, it's a similar structure to [[.df ]]in Python). You can rename the [[Map ]]frame if your ESRI GUI becomes stacked with [[Map ]]frames on a complicated project.

If you want to perform different manipulations on the data for different purposes, please load the raw data from your [[\\\_datacopy]] folder into a new [[Map ]]frame.

Yes! Now you see why you create copies of data.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/7648abf7-a00e-4a4e-893f-efcfa53652d2/ascreenshot.jpeg?tl_px=0,0&br_px=1376,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=15,224)


35\. Click [[Properties ]]on the [[Map ]]frame

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/30ff068b-66ed-436f-a4d7-3c1aee6f4c3d/ascreenshot.jpeg?tl_px=0,310&br_px=1376,1080&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=62,371)


36\. Lets now inspect which **Coordinate Reference System(s)** are controlling how we see our data.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/accf80d9-8239-471a-a631-494d953349d3/ascreenshot.jpeg?tl_px=0,0&br_px=1376,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=472,200)


37\. As mentioned earlier during data collection, Natural Earth builds their datasets in the [[WGS 1984 GCS]] since its intended for users at a global scale. And WGS 1984 is the default for world scale across computing environments.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/11021567-7a69-42bd-81e8-1d07c850e993/ascreenshot.jpeg?tl_px=100,54&br_px=1477,823&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=524,277)


38\. Right click on [[US States]] to activate its properties panel

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/70b688a0-cf80-436c-8988-0cf3531e0497/ascreenshot.jpeg?tl_px=0,13&br_px=1376,782&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=42,277)


39\. Upon inspecting the [[US States]] layer, we can learn more about the components of the [[WGS 1984 GCS]] properties controlling the Map frame.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/66f8d808-2e52-4677-b9fa-3132d3b44a74/user_cropped_screenshot.webp?tl_px=0,0&br_px=1141,730&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=883,654)


40\. So, after inspecting the properties of the controlling GIS data layer, we know the world being presented to us is from the perspective of [[WGS 1984]].

Considering the scope of my project discussed at the beginning of lab, i*s WGS 1984 the most appropriate GCS/PCS system for my cartographic image?*

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/2c12fee2-e4fc-46cd-8079-1b7dee5748a2/ascreenshot.jpeg?tl_px=0,6&br_px=1919,1080&force_format=jpeg&q=100&width=1120.0)


41\. Navigate to the properties of the [[Great Basin]] layer to learn how the Nevada Bureau of Mines and Geology collected the data.

We learn that it was collected at the [[NAD 1983 Datum]] for the **GCS**, and the data is best projected at the [[NAD 1983 UTM Zone 11N]] **PCS**. With the cartographic image being distorted in a [[Transverse Mercator]] **projection**.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/d1fc9cdd-c107-45ad-ac1f-c48d7b27b1d4/user_cropped_screenshot.webp?tl_px=0,0&br_px=1172,742&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=873,638)


42\. Okay, so now we have an idea of the spatial manipulation we need to do to our data. 

Navigate to [[Tools]].

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/71dab089-d1e0-4687-b58e-cdf6e8532c9a/ascreenshot.jpeg?tl_px=0,0&br_px=1376,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=189,51)


43\. Find the [[Project ]]tool

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/3c9b1f66-d8f7-4207-bb7d-6971f9f14052/ascreenshot.jpeg?tl_px=544,0&br_px=1920,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=856,177)


44\. Input your [[US States]] layer into the first dialog prompt

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/98100f28-a49f-4a14-b893-a27dc5f0be4e/File.jpeg?tl_px=544,0&br_px=1920,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=869,243)


45\. Rename the output dataset to something which will make sense to you in the future, and ensure the output dataset will be sent to your [[Data ]]folder. 

Select the [[Great Basin]] layer as the GCS/PCS properties to be transformed onto the [[US States]] layer.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/20dc96b3-efc6-4c12-bbc9-964908f9747f/File.jpeg?tl_px=544,71&br_px=1920,840&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=884,276)


46\. After running the [[Project ]]tool, you will notice you have a new data layer.

This is the [[US States]] layer with the **UTM Zone 11N** and **NAD 1983** properties structured into its composition.

Alaska and Hawaii are... sorta missing? More on that in a later step.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/5679d7a3-dc4c-486b-8a5a-e439adab8431/File.jpeg?tl_px=0,65&br_px=1376,834&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=29,277)


47\. After renaming the newly projected layer, ensure the [[drawing order]] is restored.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/45dd8114-ac02-4411-a01b-5182831ff75f/File.jpeg?tl_px=0,59&br_px=1376,828&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=-5,276)


48\. Inserting the reference basemap is perfect for instances when you need to troubleshoot an action you commanded your data to do.

Using the basemap reference, we can see that how the **GCS** is influencing the data. Parts of Hawaii, Alaska and the Northeast are missing since parts of those polygons were not *located* on the the **NAD 1983 GCS** when it was *projected* in **UTM Zone 11N**.

Now... what happens when we change the [[Map ]]frame **projection** to Transverse Mercator and our data is *drawn* onto a 2-D representation surface specific to the Great Basin region?

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/ff33d415-69a3-4bb2-9531-c607bcb0b54e/File.jpeg?tl_px=0,226&br_px=1376,995&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=498,277)


49\. Right click [[Map]]

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/6dba4769-0644-4e55-bbd4-e0d419e529ee/File.jpeg?tl_px=0,0&br_px=1376,769&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=16,228)


50\. Click [[Properties]]

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/9ff49fbf-36d7-41b9-857e-19287dfeee0c/File.jpeg?tl_px=0,310&br_px=1376,1080&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=62,373)


51\. Unlike the specific properties panel for each individual layer, the [[Coordinate Systems]] panel for the [[Map ]]frame allows us to do a 'Projection On-the-Fly'. Here, we are switching the **CRS** system controlling the visual perception from **WGS 1984** to **NAD 1983 UTM Zone 11N** (a detailed inspection of the **CRS** properties will show that it contains the **GCS/PCS/Projection** components previously outlined).

**Projection On-the-Fly** *does not* alter the composition of your original data, which is why we did that laborious step previously of converting the U.S. States layer into **NAD1983** and **UTM Zone 11N**

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/6fa7dc90-835d-4dfa-8da7-7d4779f8ae3e/File.jpeg?tl_px=544,310&br_px=1920,1080&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=851,462)


52\. Woah! Now we're seeing things a bit differently.

Hey, I wonder how this Projection On-the-Fly altered my basemap reference?

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/82c377b4-caf8-473b-a474-3db2c5e034d1/File.jpeg?tl_px=0,60&br_px=1376,829&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=-4,277)


53\. Oh... it totally altered the *world as you see it, through the [mathematics of Transverse Mercator](https://www.e-education.psu.edu/natureofgeoinfo/c2_p22.html)*.

And, since we took that [[Projection ]]step earlier, it altered the underlying structure of the data. The two datasets we collected earlier both now align to the contextually appropriate **CRS** for the project scope and scale.

If you are currently taking LDARCH 188, you might now be connecting the dots on how setting the **CRS** for the entire [[Map ]]frame will have a huge impact on the spatial analysis, cartographic image and the landscape narrative you are able to tell.

Recall the slide from lecture showing how a slight change in the [[Map ]]frame **CRS** altered the measurement of the buffer zone.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/ce24356c-9bcb-4407-9c9d-9b26bc3402e1/File.jpeg?tl_px=44,310&br_px=1420,1080&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=524,402)


54\. Pan around your new *World* and reflect on the content from last week's lectures.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/8fee8951-e563-401d-b8fa-12f4c515b813/File.jpeg?tl_px=211,310&br_px=1588,1080&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=524,296)


55\. Before moving on to the lab prompts, make sure to alter the [[Extent ]]you think would be appropriate for the data.

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/7153b609-c6ca-4441-8ec1-abfa776cda32/File.jpeg?tl_px=0,310&br_px=1376,1080&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=181,535)


56\. How does it feel now that you've completed the whole process? 

Are you ready to do this independently, and carry the weight of responsibly mapping the landscape?

![](https://ajeuwbhvhr.cloudimg.io/https://colony-recorder.s3.amazonaws.com/files/2025-09-27/ecf59737-2958-44b1-b294-da5859aa5ef9/File.jpeg?tl_px=0,310&br_px=1376,1080&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=0.7&wat_gravity=northwest&wat_url=https://colony-recorder.s3.us-west-1.amazonaws.com/images/watermarks/FB923C_standard.png&wat_pad=444,320)
#### [Made with Scribe](https://scribehow.com/shared/Lab_6_-_Projection__MR2X2m2KRSan4Jm8zmJ8ow)



