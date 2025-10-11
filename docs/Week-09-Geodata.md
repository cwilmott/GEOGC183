# Week 09 Geodata

This exercise asks you to:
- digitize historic landmarks from the Berkeley Architectural Heritage Association (BAHA), and;
- set up Github as a host for this data, and your future web map. 

We will be using geoJSON as the key data format.

## Foundations Pathway

!!! tip "For Tech-Tortoises"
    This pathway is for those who want to go through slowly and carefully, learning the fundamentals and foundations of web mapping.       If you're technologically nervous, or like lots of instructions, choose this path!

### Create Your GeoJSON

This tasks asks you to manually geolocate a ten data points from the BAHA.  

#### Find your Data
- Open your web browser
	* In one tab, *Tab-BAHA* go to <https://berkeleyheritage.com/berkeley_landmarks/all_landmarks.html>
	* In another tab, *Tab-JSON*, go to <geojson.io>
- In *Tab-BAHA* on the BAHA Site, select 10 buildings you would like to digitize.

#### Start Digitizing
- In *Tab-BAHA*, copy (++control+c++) the street address from the table.
- In *Tab-JSON*, paste (++control+v++) the street address in the search bar. This should take you to the address in Berkeley. If not, you may need to look it up.
    * Select the "Point" marker from the toolbar on the right - when you toggle, it says *Draw Point (m)* - or press ++m++ on the keyboard.
    * Place the marker on the map.

#### Add Feature Categories (or variables)
- Still in *Tab-JSON*, now select the tab on the right-hand side which says **Table**.
- Then select **new column**
    * In the new column pop-up, write "Landmark"
- Repeat this step for the following categories:
    * "Address"
    * "Architect + Date"
    * "Link"
    * "Designated"
    * "Notes"
- Then copy (++control+c++) and paste (++control+v++) the information for each of the categories.

!!! info "For the Link Column"
     Right-click on the "Landmark" name (if it is underlined) and select *"Copy Link Address"* to fill in the "Link" Column.

#### Fill out your GeoJSON Feature Collection

Now, repeat these steps for each address:
- Search for the address
- Select the point tool
- Make a point
- Fill Out the Column Data

!!! warning
    Don't forget to save periodically to avoid losing your work. geojson.io has become finicky recently, but we haven't found a better replacement. To do this choose *Save > geoJSON*. Tell your instructor when you do this so we can see where it is saving.

#### Export your GeoJSON

When you're done, you're ready to export your GeoJSON for the final time.
- Go to *Save* and choose *geoJSON*
- Find the location of the *last* geojson you saved, and rename it "183data.geojson". (2) DO NOT CLOSE THIS FOLDER.
{ .annotate }
2. 	To rename a folder, right click and select "rename"

### Set up your Github

Now we need somewhere to put your new .geojson file! Github is a free repository where we can put code and share it with other people - one of the cornerstones of open source (for free) software development. It has the added bonus of also being a web-publisher, where we can actually host relatively sophisticated websites.

#### Sign Up to Github

 - In your browser, create a new window or tab, and navigate to <https://github.com/>
 - On the top-right of the page, select *Sign Up* . I like to use my Berkeley credentials, but you may want to use your personal email as well. (3) { .annotate }
3. 	Github provides lots of support for the sign up process here: <https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github>

#### Set Up A Repository
- In the upper-right corner of any page, select, then click *New repository*.
![New Repository]([https://dummyimage.com/600x400/eee/aaa](https://docs.github.com/assets/cb-29762/mw-1440/images/help/repository/repo-create-global-nav-update.webp ){ align=left }
- In the "Repository name" box, type **BAHA Map**
- In the "Description" box, type a short description. For example, type "This repository is for the BAHA Map"
- Select *Public* for your repository.
- Select *Add a README file*.
- Click *Create repository*.


### Add your Data
### Publish to Web Using Github Pages

## Experimental Pathway
!!! tip "For Tech-Hares"
	This pathway is for students who love to bash at things until they work, and run before they can walk. If you have low attention spans and lots of tech confidence, this is the pathway for you. 
	
### Scrape + Clean Data
This pathway asks you to scrape and clean data from the BAHA website, rather than manually create a dataset.

#### Examine the Code Structure.
The first thing you need to do is examine the HTML code structure: how is the data you'd like to scrape structured? <br>
 - Go to the BAHA website at <https://berkeleyheritage.com/berkeley_landmarks/all_landmarks.html>
 - Choose a list of 100 sites and click.
 - Right-click on the table with the data and select *Inspect*, *View Page Source*, *Developer Tools* - or similar.
    * You will see that the code is nested in a <table> tag, with sub-tags ```<td>``` and ```<tr>```. This means that the data is structured as a table within the HTML page.

#### Scrape Data 
There are lots (and lots!) of ways to scrape data (hit Clancy up if you'd like to know more and you're good at .py), but one of the easiest is actually using Google Sheets. Since the data is in a table, we can use the ```IMPORTHTML``` function.
 - Create a Google Sheet
 - Select the top left corner cell 
 - Then, use the IMPORTHTML function to scrape the data following the syntax here: <https://support.google.com/docs/answer/3093339?hl=en>
     *See if you can figure out how to format the syntax on your own first, otherwise, here is a hint (1). { .annotate }
   
1.   Functions start with = . This worked for me:  ``` javascript
    =IMPORTHTML("https://berkeleyheritage.com/berkeley_landmarks/landmarks1-100.html", "table", 1, "en_US")
    ```

#### Geocode the Data
Now that you [should] have the data imported as a table, you can start to work with the data. If you're familar with python, you may find it easier to do this using data wrangling, but honestly, if someone has made a decent tool already, why not start there?

 - Start by exporting your new Feature Collection to **.csv**
 - Then, we need to *geocode* the address data into x and y coordinates. To do this, while ArcGIS and QGIS both have geocoders, it's sometimes easier to find a lighter solution online. Have a look around and see what you can find. This one worked okay for me <https://www.geoapify.com/tools/geocoding-online/>
       * If you'd like to learn more about how geocoding works, see <https://www.mapbox.com/insights/geocoding>

#### Convert the Data

For some reason, you can't just easily open the geocoded CSV into geojson.io - this is a new bug, and it's super annoying. 
BUT, it's easier to just convert the data, rather than fight with it. 

There are lots of good csv to geoJSON converters out there. Again, have a search, but this one worked for me (the Czech are *great* for open source tools): <https://mygeodata.cloud/converter/csv-to-geojson> 

#### Export and Save

Now you should be able to upload the data to geojson.io, using the "Open" option.
 - Clean the data as you see fit, and then *Save > geoJSON*
 - Locate the downloaded file, and rename it to 183data.geosjon

### Set up your Github
### Build your File Structure
Once you've set up your Github Repository, you'll need to add a folder to the repositoy to put your 183data.geojson file in.
- 
### Publish to Web
### Make A Basic HTML Page 
If you're feeling confident, and you still have 15-30 mins left, you can start messing around with HTML. 

Code Pen is a good place to start, alongside W3 Schools. See if you can figure out how to style text, and add links. This will be useful for Lab 10.

### Hints








