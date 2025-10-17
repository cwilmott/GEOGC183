# Week 10 Mapbox Basemap

## Foundations :turtle:

Let's take it *slllooooowww*. Breathe!

### Mapbox
First, we need to create our very own *Mapbox* map. Mapbox is a semi-open source tool we can use to make web maps. Its data is based on *OpenStreetMap*, and we get *a lot* of free views so it's a useful tool to begin your first web map. 

#### Set up Mapbox
So, let's head over to <www.mapbox.com> . In the top-right corner select **Sign Up**. <br>
Enter the credentials you wish to use, and set up your account.

#### Create a Mapbox Style

Now that you're successfully in Mapbox, let's create a custom map style!

Open the *Mapbox Studio* styles page, where all your map styles will be listed.
Click the drop down next to the **New Style** button.
Select **Classic** template.
Select the **Monochrome** style.
Choose a base variation.These colors can be adjusted later.
Click **Customize Monochrome**.

![Mapbox](assets/map-styles-style-templates.gif)

Once you're in, have a play around with different styles and have some fun - change some fonts, and see if you can establish a different color scheme based on our lectures last week.
If you'd like to learn more (or be more intentional), check out <https://docs.mapbox.com/studio-manual/reference/styles/>

#### Publish your Style
Once you're done with your style, we need to make sure it's publically visible before we put it in our web map!

The **Publish** button in the upper right of the style editor allows you to save your style so you can use it.
When you click **Publish** the following information appears:

![Image Title](https://docs.mapbox.com/studio-manual/assets/ideal-img/overview-publish-share-production.2823d1b.960.png)

We're going to publish to web, so at the bottom you'll need to save these two pieces of code somewhere safe (but don't worry, you can always get them back!):<br>
```Style URL``` - this is the unique identifier of your map
``` Mapbox Token ``` - this is a secret code which links to your Mapbox Account.

### Create Your Web Map
So now we are going to create a very basic framework to host your webmap using Github. We will use **Code Pen** while we get used to coding in html/css/js - and then export the as a .zip file, and upload it to Github.

#### Set up Code Pen
The first thing you need to do is set up a Code Pen account - if you haven't already. 

Go to <https://codepen.io/> and choose "Sign Up". You may sign up with either your email or your github account.

On the top right, under the "Create" submenu, select **Pen**, then, **Pen**.

Your page should look like this:

![Code Pen](assets/codepen.jpg)

As you may remember from lecture, code pen has three windows - one for HTML, one for CSS and one for .js - we will be putting different pieces of code into different windows! And remember, nothing is broken for ever! 

**Now, let's start coding!**

#### Set up your HTML

First, we need to create a HTML container for your web map to be held in. We're going to use the ```<div>``` tag to create a division to hold your map.

In the HTML box, either type or copy and paste the below code:

```
html <div id="map"></div> 
```

This code bascially means "this is a division, with the id of "map". 
Nothing will change, because it's just an invisible structure! We haven't put anything into it yet!

#### Set Up Your CSS

Next, we need to style your map <div> using CSS. You can choose how big or small you want your map to be in future, but to make it easier for now, we are going to make the map full page, with no margins and to be 100% the width of the web browser.

Your css component, thus has two components: a style for the ```<body>``` (```body```) and a style for the ```<div id=map>``` (```#map```)

``` css
body {
margin: 0;
padding: 0;
}
#map {
position: absolute;
top: 0;
bottom: 0;
width: 100%; }
```
The "position" element in #map sets *where* on the page your map sits - 

#### Set up Your .js



### Transfer to Github

#### Export

#### Upload Files

#### Check its worked!



## Experimental :rabbit2:

### Mapbox
#### Set up Mapbox

#### Create a Mapbox Style

#### Publish your Style

### Create Your Web Map

#### Set up Visual Studio Code

#### Create your HTML file

#### Create your CSS file

#### Create your .js file

### Transfer to Github

#### Upload Files

#### Check its worked!




