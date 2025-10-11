# Week 09 Geodata

This exercise asks you to a) digitize historic landmarks from the Berkeley Architectural Heritage Association (BAHA) and b) set up Github as a host for this data, and your future web map. 

We will be using geoJSON as the key data format.

### Foundations Pathway

!!! tip "For Tech-Tortoises"
    This pathway is for those who want to go through slowly and carefully, learning the fundamentals and foundations of web mapping.       If you're technologically nervous, or like lots of instructions, choose this path!

#### Create Your GeoJSON
This tasks asks you to manually geolocate a ten data points from the BAHA.  
##### Find your Data
- Open your web browser
	* In one tab, *Tab-BAHA* go to https://berkeleyheritage.com/berkeley_landmarks/all_landmarks.html
	* In another tab, "Tab-JSON", go to geojson.io
- In "Tab-A" on the BAHA Site, select 10 buildings you would like to digitize.

##### Start Digitizing
- In *Tab-BAHA*, copy (++control+c++) the street address from the table.
- In *Tab-JSON*, paste (++control+v++) the street address in the search bar. This should take you to the address in Berkeley. If not, you may need to look it up.
    * Select the "Point" marker from the toolbar on the right (when you toggle, it says "Draw Point (m)") or press ++m++ on the keyboard.
    * Place the marker on the map.

##### Add Categories (or variables)
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
!!! tip "For the Link Column"
    Right-click on the "Landmark" name (if it is underlined) and select *"Copy Link Address"* to fill in the "Link" Column.

##### Fill out your GeoJSON

Now, repeat these steps for each address:
- Search for the address
- Select the point tool
- Make a point
- Fill Out the Column Data

!!! warning
Don't forget to save periodically to avoid losing your work. geojson.io has become finicky recently, but we haven't found a better replacement. To do this choose *Save > geoJSON*. Tell your instructor when you do this so we can see where it is saving.

##### Export your GeoJSON

When you're done, you're ready to export your GeoJSON for the final time.
- Go to *Save* and choose *geoJSON*
- Find the location of the *last* geojson you saved, and rename it "183data.geojson". DO NOT CLOSE THIS FOLDER.

#### Set up your Github
#### Set Up Folders
#### Publish to Web

### Experimental Pathway
!!! tip "For Tech-Hares"
	This pathway is for students who love to bash at things until they work, and run before they can walk. If you have low attention spans and lots of tech confidence, this is the pathway for you. 
#### Scrape + Clean Data

#### Set up your Github
#### Build your File Structure
#### Publish to Web
#### Make A Basic HTML Page 


