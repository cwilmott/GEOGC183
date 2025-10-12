# Week 09 Geodata

This exercise asks you to: <br>
 - digitize historic landmarks from the Berkeley Architectural Heritage Association (BAHA), and; <br>
 - set up Github as a host for this data, and your future web map. 

We will be using ```geoJSON``` as the key data format.

## Foundations Pathway :turtle:

!!! tip "For Tech-Tortoises"
    This pathway is for those who want to go through slowly and carefully, learning the fundamentals and foundations of web mapping.<br>
	If you're technologically nervous, or like lots of instructions, choose this path!

### Create Your GeoJSON

This tasks asks you to manually geolocate 10 data points from the BAHA.  

#### Find your Data
:material-numeric-1-circle: Open your web browser <br>
	* :material-arrow-right-bottom: In one tab, **Tab-BAHA** go to <https://berkeleyheritage.com/berkeley_landmarks/all_landmarks.html> <br>
	* :material-arrow-right-bottom: In another tab, **Tab-JSON**, go to <https://geojson.io> <br>
:material-numeric-2-circle: In **Tab-BAHA** on the BAHA Site, select 10 buildings you would like to digitize.<br>

#### Start Digitizing
:material-numeric-1-circle: In **Tab-BAHA**, copy (++control+c++) the **street address** from the table.<br>
:material-numeric-2-circle: In **Tab-JSON**, paste (++control+v++) the street address in the **search bar**. This should take you to the address in Berkeley. If not, you may need to find it on the map. <br>
:material-numeric-3-circle: Select the "Point" marker from the toolbar on the right - when you toggle, it says *Draw Point (m)* - or press ++m++ on the keyboard.<br>
:material-numeric-4-circle: Place the marker on the map.<br>

#### Add Feature Categories (or variables)
:material-numeric-1-circle: Still in **Tab-JSON**, now select the tab on the right-hand side which says **Table**.<br>
:material-numeric-2-circle: Then select **new column**<br>
	:octicons-dot-16: In the new column pop-up, write "Landmark"<br>
:material-numeric-3-circle: Repeat this step for the following categories:<br>
    * "Address"
    * "Architect + Date"
    * ["Link"]("**Right-Click** on the **Landmark Name** (if it is underlined) and select **Copy Link Address** to fill in the "Link" column")
    * "Designated"<br>
    * "Notes"<br>
:material-numeric-4-circle: Then copy (++control+c++) and paste (++control+v++) the information for each of the categories. <br>


#### Fill out your GeoJSON Feature Collection

Now, repeat these steps for each address: <br>
:material-arrow-right-bottom: Search for the address
:material-arrow-right-bottom: Select the point tool
:material-arrow-right-bottom: Make a point
:material-arrow-right-bottom: Fill Out the Column Data

!!! warning
    Don't forget to save periodically to avoid losing your work. geojson.io has become finicky recently, but we haven't found a better replacement. To do this choose *Save > geoJSON*. Tell your instructor if you're one of the first to do this, so we can see where it is saving.

#### Export your GeoJSON

When you're done, you're ready to export your GeoJSON for the final time. <br>

:material-numeric-1-circle: Go to **Save** and choose **geoJSON** <br>
:material-numeric-2-circle: Find the location of the *last* geojson you saved, and [rename]("To rename a folder, **right click** and select **rename**") it ```183data.geojson```. Don't close the folder.
 

### Set up your Github

Now we need somewhere to put your new ```.geojson``` file! Github is a free repository where we can put code and share it with other people - one of the cornerstones of open source (for free) software development. It has the added bonus of also being a web-publisher, where we can actually host relatively sophisticated websites.

#### Sign Up to Github

:material-numeric-1-circle: In your browser, create a new window or tab, and navigate to <https://github.com/> <br>
:material-numeric-2-circle: On the top-right of the page, select [**Sign Up**](<https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github> "Github provides lots of support for the sign up process here"). I like to use my Berkeley credentials, but you may want to use your personal email as well. 

#### Set Up A Repository
Let's set up a repository to hold your hard-earned data. 
:material-numeric-1-circle: In the upper-right corner of any page, select, then click *New repository*. <br>
![New Repository](https://docs.github.com/assets/cb-29762/mw-1440/images/help/repository/repo-create-global-nav-update.webp ) <br>
:material-numeric-2-circle: In the "Repository name" box, type **BAHA Map** <br>
:material-numeric-3-circle: In the "Description" box, type a short description. For example, type "This repository is for the BAHA Map" <br>
:material-numeric-4-circle: Select **Public** for your repository. <br>
:material-numeric-5-circle: Select **Add a README file**. <br>
:material-numeric-6-circle: Click **Create repository**. <br>

### Add your Data
Now that you have your Github account up and running, we need to create a basic file structure to house your data. It's not hard.

So far, you should only see one file listed in the repository, the ```README.md``` file you created when you initialized the repository. Now, we'll upload some of our own files.

 :material-numeric-1-circle: To the right of the page, select the **Add file** dropdown menu. <br>
 :material-numeric-2-circle: From the dropdown menu, click *Upload* files. <br>
 :material-numeric-3-circle: On your computer, return to the the folder containing your ```183data.geojson``` file, then drag and drop it into the browser. <br>
 :material-numeric-4-circle: At the bottom of the page, under "Commit changes", select "Commit directly to the main branch, then click **Commit changes**. <br>

#### Tidy Your Files
We don't want this to be in the main section because it's untidy (and you might end up with many more data files!), so we want to make a new folder. <br>
:material-numeric-1-circle: To do this, you need to select the 183data.geojson file. <br>
:material-numeric-2-circle: Then, select the "Edit" icon to edit this file. <br>
![Image title](https://docs.github.com/assets/cb-47646/mw-1440/images/help/repository/edit-file-edit-button.webp)
:material-numeric-3-circle: Then, locate the file structure bar at the top. <br>
:material-numeric-4-circle: Copy and paste (or write directly) ``` /data ```  into the file structure bar <br>
![Image title](https://docs.github.com/assets/cb-29857/mw-1440/images/help/repository/changing-file-name.webp)

### Publish to Web Using Github Pages

## Experimental Pathway :rabbit2:
!!! tip "For Tech-Hares"
	This pathway is for students who love to bash at things until they work, and run before they can walk. If you have low attention spans and lots of tech confidence, this is the pathway for you. 
	
### Scrape + Clean Data
This pathway asks you to scrape and clean data from the BAHA website, rather than manually create a dataset.

#### Examine the Code Structure.
The first thing you need to do is examine the HTML code structure: how is the data you'd like to scrape structured? <br>
:material-numeric-1-circle: Go to the BAHA website at <https://berkeleyheritage.com/berkeley_landmarks/all_landmarks.html> <br>
:material-numeric-2-circle: Choose a list of 100 sites and click. <br>
:material-numeric-3-circle: Right-click on the table with the data and select *Inspect*, *View Page Source*, *Developer Tools* - or similar. <br>
    :material-arrow-right-bottom: You will see that the code is nested in a ```<table>``` tag, with sub-tags ```<td>``` and ```<tr>```. This means that the data is structured as a table within the HTML page.

#### Scrape Data 
There are lots (and lots!) of ways to scrape data (hit Clancy up if you'd like to know more and you're good at .py), but one of the easiest is actually using Google Sheets. Since the data is in a table, we can use the ```IMPORTHTML``` function. <br>
:material-numeric-1-circle: Create a Google Sheet <br>
:material-numeric-2-circle: Select the top left corner cell <br>
:material-numeric-3-circle: Then, use the IMPORTHTML function to scrape the data following the syntax here: <https://support.google.com/docs/answer/3093339?hl=en> . See if you can figure out how to format the syntax on your own first, otherwise, here is a hint (1)
{ .annotate }
   
1.   Functions start with ```=```. This worked for me:  ```
    =IMPORTHTML("https://berkeleyheritage.com/berkeley_landmarks/landmarks1-100.html", "table", 1, "en_US")
    ```

#### Geocode the Data
Now that you [should] have the data imported as a table, you can start to work with the data. If you're familar with python, you may find it easier to do this using data wrangling, but honestly, if someone has made a decent tool already, why not start there? We're going to use a few free web tools to help us manage our data. <br>

:material-numeric-1-circle: Start by exporting your new Feature Collection to **.csv** <br>
:material-numeric-2-circle: Then, we need to *geocode* the address data into ```x``` and ```y``` coordinates. To do this, while ArcGIS and QGIS both have geocoders, it's sometimes easier to find a lighter solution online. Have a look around and see what you can find. This one worked okay for me <https://www.geoapify.com/tools/geocoding-online/>. If you'd like to learn more about how geocoding works, see <https://www.mapbox.com/insights/geocoding>

#### Convert the Data

For some reason, you can't just easily open the geocoded CSV into geojson.io - this is a new bug, and it's super annoying. 
BUT, it's easier to just convert the data, rather than fight with geojson.io . 

There are lots of good csv to geoJSON converters out there. Again, have a search, but this one worked for me (the Czech are *great* for open source tools). I used this one: <https://mygeodata.cloud/converter/csv-to-geojson> 

#### Export and Save

Now you should be able to upload the data to geojson.io, using the "Open" option. <br>
   :material-numeric-1-circle: Clean the data as you see fit, and then *Save > geoJSON* <br>
   :material-numeric-2-circle: Locate the downloaded file, and rename it to **183data.geosjon** <br>

### Set up your Github
### Build your File Structure

Once you've set up your Github Repository, you'll need to add a folder to the repositoy to put your 183data.geojson file in.

### Publish to Web
### Make A Basic HTML Page 
If you're feeling confident, and you still have 15-30 mins left, you can start messing around with HTML. 

Code Pen is a good place to start, alongside W3 Schools. See if you can figure out how to style text, and add links. This will be useful for Lab 10.























