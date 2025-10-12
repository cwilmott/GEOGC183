# Week 09 Geodata

This exercise asks you to:
 - digitize historic landmarks from the Berkeley Architectural Heritage Association (BAHA), and;
 - set up Github as a host for this data, and your future web map. 

We will be using ```geoJSON``` as the key data format.

Lorem ipsum dolor sit amet, (1) consectetur adipiscing elit.
{ .annotate }

1.  :man_raising_hand: I'm an annotation! I can contain `code`, __formatted
    text__, images, ... basically anything that can be expressed in Markdown.

## Foundations Pathway

!!! tip "For Tech-Tortoises"
    This pathway is for those who want to go through slowly and carefully, learning the fundamentals and foundations of web mapping.<br>
	If you're technologically nervous, or like lots of instructions, choose this path!

### Create Your GeoJSON

This tasks asks you to manually geolocate 10 data points from the BAHA.  

#### Find your Data
:material-numeric-1-circle: Open your web browser
 - In one tab, **Tab-BAHA** go to <https://berkeleyheritage.com/berkeley_landmarks/all_landmarks.html>
 - In another tab, **Tab-JSON**, go to <https://geojson.io>
:material-numeric-2-circle: In **Tab-BAHA** on the BAHA Site, select 10 buildings you would like to digitize.

#### Start Digitizing
:material-numeric-1-circle: In **Tab-BAHA**, copy (++control+c++) the **street address** from the table.
:material-numeric-2-circle: In **Tab-JSON**, paste (++control+v++) the street address in the **search bar**. This should take you to the address in Berkeley. If not, you may need to find it on the map.
:material-numeric-3-circle: Select the "Point" marker from the toolbar on the right - when you toggle, it says *Draw Point (m)* - or press ++m++ on the keyboard.
:material-numeric-4-circle: Place the marker on the map.

#### Add Feature Categories (or variables)
:material-numeric-1-circle: Still in **Tab-JSON**, now select the tab on the right-hand side which says **Table**.
:material-numeric-2-circle: Then select **new column**
	:octicons-dot-16: In the new column pop-up, write "Landmark"
:material-numeric-3-circle: Repeat this step for the following categories:
	:octicons-dot-16: "Address"
	:octicons-dot-16:"Architect + Date"
<div class="annotate" markdown>
	:octicons-dot-16: "Link" (1)
</div>
	:octicons-dot-16: "Designated"
	:octicons-dot-16: "Notes"
:material-numeric-4-circle: Then copy (++control+c++) and paste (++control+v++) the information for each of the categories.
{.annotate}
1.  **Right-Click** on the **Landmark Name** (if it is underlined) and select **Copy Link Address** to fill in the "Link" column. 

#### Fill out your GeoJSON Feature Collection

Now, repeat these steps for each address:
- Search for the address
- Select the point tool
- Make a point
- Fill Out the Column Data

!!! warning
    Don't forget to save periodically to avoid losing your work. geojson.io has become finicky recently, but we haven't found a better replacement. To do this choose *Save > geoJSON*. Tell your instructor if you're one of the first to do this, so we can see where it is saving.

#### Export your GeoJSON

When you're done, you're ready to export your GeoJSON for the final time.

:material-numeric-1-circle: Go to **Save** and choose **geoJSON**
:material-numeric-2-circle: Find the location of the *last* geojson you saved, and rename it ```183data.geojson``` (2). DO NOT CLOSE THIS FOLDER.
{ .annotate }

2. 	To rename a folder, **right click** and select **rename**


### Set up your Github

Now we need somewhere to put your new ```.geojson``` file! Github is a free repository where we can put code and share it with other people - one of the cornerstones of open source (for free) software development. It has the added bonus of also being a web-publisher, where we can actually host relatively sophisticated websites.

#### Sign Up to Github

:material-numeric-1-circle: In your browser, create a new window or tab, and navigate to <https://github.com/>
:material-numeric-2-circle: On the top-right of the page, select **Sign Up** (3). I like to use my Berkeley credentials, but you may want to use your personal email as well.
{ .annotate }
3. 	Github provides lots of support for the sign up process here: <https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github>

#### Set Up A Repository
:material-numeric-1-circle: In the upper-right corner of any page, select, then click *New repository*.
![New Repository](https://docs.github.com/assets/cb-29762/mw-1440/images/help/repository/repo-create-global-nav-update.webp ){ align=left }
:material-numeric-2-circle: In the "Repository name" box, type **BAHA Map**
:material-numeric-3-circle: In the "Description" box, type a short description. For example, type "This repository is for the BAHA Map"
:material-numeric-4-circle: Select **Public** for your repository.
:material-numeric-5-circle: Select **Add a README file**.
:material-numeric-6-circle: Click **Create repository**.

### Add your Data
Now that you have your Github account up and running, we need to create a basic file structure to house your data. It's not hard.

So far, you should only see one file listed in the repository, the ```README.md``` file you created when you initialized the repository. Now, we'll upload some of our own files.

:material-numeric-1-circle: To the right of the page, select the **Add file** dropdown menu.
:material-numeric-2-circle: From the dropdown menu, click *Upload* files.
:material-numeric-3-circle: On your computer, return to the the folder containing your ```183data.geojson``` file, then drag and drop it into the browser.
:material-numeric-4-circle: At the bottom of the page, under "Commit changes", select "Commit directly to the main branch, then click **Commit changes**.

#### Tidy Your Files
We don't want this to be in the main section because it's untidy (and you might end up with many more data files!), so we want to make a new folder. <br>
:material-numeric-1-circle: To do this, you need to select the 183data.geojson file.
:material-numeric-2-circle: Then, select the "Edit" icon to edit this file.
![Image title](https://docs.github.com/assets/cb-47646/mw-1440/images/help/repository/edit-file-edit-button.webp){align=right}
:material-numeric-3-circle: Then, locate the file structure bar at the top. 
:material-numeric-4-circle: Copy and paste (or write directly) ``` /data ```  into the file structure bar
![Image title](https://docs.github.com/assets/cb-29857/mw-1440/images/help/repository/changing-file-name.webp){align=right}

### Publish to Web Using Github Pages

## Experimental Pathway
!!! tip "For Tech-Hares"
	This pathway is for students who love to bash at things until they work, and run before they can walk. If you have low attention spans and lots of tech confidence, this is the pathway for you. 
	
### Scrape + Clean Data
This pathway asks you to scrape and clean data from the BAHA website, rather than manually create a dataset.

#### Examine the Code Structure.
The first thing you need to do is examine the HTML code structure: how is the data you'd like to scrape structured? <br>
:material-numeric-1-circle: Go to the BAHA website at <https://berkeleyheritage.com/berkeley_landmarks/all_landmarks.html> <br>
:material-numeric-2-circle: Choose a list of 100 sites and click.
:material-numeric-3-circle: Right-click on the table with the data and select *Inspect*, *View Page Source*, *Developer Tools* - or similar.
	:material-arrow-right-bottom: You will see that the code is nested in a ```<table>``` tag, with sub-tags ```<td>``` and ```<tr>```. This means that the data is structured as a table within the HTML page.

#### Scrape Data 
There are lots (and lots!) of ways to scrape data (hit Clancy up if you'd like to know more and you're good at .py), but one of the easiest is actually using Google Sheets. Since the data is in a table, we can use the ```IMPORTHTML``` function. <br>
:material-numeric-1-circle: Create a Google Sheet
:material-numeric-2-circle: Select the top left corner cell 
:material-numeric-3-circle: Then, use the IMPORTHTML function to scrape the data following the syntax here: <https://support.google.com/docs/answer/3093339?hl=en> . See if you can figure out how to format the syntax on your own first, otherwise, here is a hint (1)
{ .annotate }
   
1.   Functions start with ```=```. This worked for me:  ```
    =IMPORTHTML("https://berkeleyheritage.com/berkeley_landmarks/landmarks1-100.html", "table", 1, "en_US")
    ```

#### Geocode the Data
Now that you [should] have the data imported as a table, you can start to work with the data. If you're familar with python, you may find it easier to do this using data wrangling, but honestly, if someone has made a decent tool already, why not start there? We're going to use a few free web tools to help us manage our data.

:material-numeric-1-circle: Start by exporting your new Feature Collection to **.csv**
:material-numeric-2-circle: Then, we need to *geocode* the address data into ```x``` and ```y``` coordinates. To do this, while ArcGIS and QGIS both have geocoders, it's sometimes easier to find a lighter solution online. Have a look around and see what you can find. This one worked okay for me <https://www.geoapify.com/tools/geocoding-online/> (4)
{ .annotate }

4.	If you'd like to learn more about how geocoding works, see <https://www.mapbox.com/insights/geocoding>

#### Convert the Data

For some reason, you can't just easily open the geocoded CSV into geojson.io - this is a new bug, and it's super annoying. 
BUT, it's easier to just convert the data, rather than fight with geojson.io . 

There are lots of good csv to geoJSON converters out there. Again, have a search, but this one worked for me (the Czech are *great* for open source tools). I used this one: <https://mygeodata.cloud/converter/csv-to-geojson> 

#### Export and Save

Now you should be able to upload the data to geojson.io, using the "Open" option.
:material-numeric-1-circle: Clean the data as you see fit, and then *Save > geoJSON*
:material-numeric-2-circle: Locate the downloaded file, and rename it to **183data.geosjon**

### Set up your Github
### Build your File Structure

Once you've set up your Github Repository, you'll need to add a folder to the repositoy to put your 183data.geojson file in.


### Publish to Web
### Make A Basic HTML Page 
If you're feeling confident, and you still have 15-30 mins left, you can start messing around with HTML. 

Code Pen is a good place to start, alongside W3 Schools. See if you can figure out how to style text, and add links. This will be useful for Lab 10.

### Hints
















